---
title: "Ajout d’un domaine à la location d’un client avec Windows PowerShell pour les partenaires avec autorisation d’accès délégué"
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 12/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: DecEntMigration
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: "Résumé : Utilisez Windows PowerShell pour Office 365 pour ajouter un autre nom de domaine à un locataire de client existant."
ms.openlocfilehash: 182750a5706dbb23c6207c6bd63334cbf2a2a795
ms.sourcegitcommit: d31cf57295e8f3d798ab971d405baf3bd3eb7a45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>Ajout d’un domaine à la location d’un client avec Windows PowerShell pour les partenaires avec autorisation d’accès délégué

 **Résumé :** Utilisez Windows PowerShell pour Office 365 pour ajouter un autre nom de domaine à un locataire de client existant.
  
Vous pouvez créer de nouveaux domaines et les associer à la location de votre client avec Windows PowerShell pour Office 365 plus rapidement qu'en utilisant le Centre d'administration Office 365.
  
Les partenaires avec autorisation d'accès délégué sont les partenaires de syndication et fournisseurs de solutions cloud. Il s'agit souvent de fournisseurs de réseau ou de télécommunication pour d'autres sociétés. Ils regroupent les abonnements Office 365 dans leurs offres de services pour les clients. Lorsqu'ils vendent un abonnement Office 365, ils bénéficient automatiquement des autorisations Administrer au nom de sur leslocations clientes. Ainsi, ils peuvent administrer les locations clientes et créer des rapports les concernant.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Ce qu’il faut savoir avant de commencer

UNRESOLVED_TOKEN_VAL(GENL_O365_PowerShell_BeforeYouBegin)
  
Vous avez également besoin des informations suivantes :
  
- Vous avez besoin du nom de domaine complet (FQDN) que votre client souhaite utiliser.
    
- Vous avez besoin du code **TenantID** du client.
    
- Le nom de domaine complet doit être enregistré auprès d'un bureau d'enregistrement de domaines DNS Internet, comme GoDaddy. Pour plus d'informations sur l'inscription publique d'un nom de domaine, voir [Comment acheter un nom de domaine](https://go.microsoft.com/fwlink/p/?LinkId=532541).
    
- Vous devez savoir comment ajouter un enregistrement TXT à la zone DNS enregistrée pour votre bureau d'enregistrement DNS. Pour plus d'informations sur la façon d'ajouter un enregistrement TXT, voir [Créer des enregistrements DNS auprès d'un fournisseur d'hébergement DNS pour Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532542). Si ces procédures ne fonctionnent pas pour vous, vous devez rechercher les procédures pour votre bureau d'enregistrement DNS.
    
## <a name="create-domains"></a>Création de domaines

 Vos clients vous demanderont probablement de créer des domaines supplémentaires à associer à leur location, car ils ne voudront probablement pas que le domaine<domain>.onmicrosoft.comsoit le domaine principal qui représente leur identité d'entreprise aux yeux du monde entier. Cette procédure vous guide au fil du processus de création d'un domaine associé à la location de votre client.
  
> [!NOTE]
> Pour effectuer certaines de ces opérations, le compte administrateur partenaire auquel vous vous connectez doit être défini sur **Administration complète** pour le paramètre **Accorder un accès administrateur aux sociétés que vous assistez** qui se trouve dans les détails du compte administrateur dans le Centre d'administration Office 365. Pour plus d'informations sur la gestion des rôles d'administrateur de partenaire, voir[Partenaires : proposer l'administration déléguée](https://go.microsoft.com/fwlink/p/?LinkId=532435). 
  
### <a name="create-the-domain-in-azure-active-directory"></a>Création du domaine dans Azure Active Directory

Cette commande crée le domaine dans Azure Active Directory, mais ne l'associe pas au domaine inscrit publiquement. Cette association a lieu lorsque vous prouvez à Microsoft Office 365 pour les entreprises que vous êtes propriétaire du domaine inscrit publiquement.
  
```
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>Obtention des données pour l’enregistrement de vérification TXT DNS

 Office 365 générera les données spécifiques que vous devrez placer dans l'enregistrement de vérification TXT DNS. Pour obtenir les données, exécutez cette commande.
  
```
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Elle vous fournira des résultats semblables à ceci :
  
 `Label: domainname.com`
  
 `Text: MS=ms########`
  
 `Ttl: 3600`
  
> [!NOTE]
> Vous aurez besoin de ce texte pour créer l’enregistrement TXT dans la zone DNS enregistrée publiquement. Copiez-le et enregistrez-le. 
  
### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a>Ajout d’un enregistrement TXT à la zone DNS enregistrée publiquement

Avant qu'Office 365 commence à accepter le trafic dirigé vers le nom de domaine enregistré publiquement, vous devez prouver que vous êtes propriétaire du domaine et que vous disposez des autorisations d'administrateur pour celui-ci. Pour prouver que vous êtes propriétaire du domaine, créez un enregistrement TXT dans le domaine. Un enregistrement TXT n'a aucun effet sur votre domaine, et il peut être supprimé une fois qu'il est établi que vous êtes propriétaire du domaine. Pour créer les enregistrements TXT, suivez les procédures décrites dans [Créer des enregistrements DNS auprès d'un fournisseur d'hébergement DNS pour Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532542). Si ces procédures ne fonctionnent pas pour vous, vous devez rechercher les procédures pour votre bureau d'enregistrement DNS.
  
Confirmez la création de l'enregistrement TXT via nslookup. Suivez cette syntaxe.
  
```
nslookup -type=TXT <FQDN of registered domain>
```

Elle vous fournira des résultats semblables à ceci :
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-office-365"></a>Confirmation de la propriété du domaine dans Office 365

Dans cette dernière étape, vous confirmez à Office 365 que vous êtes propriétaire du domaine inscrit publiquement. Après cette étape, Office 365 va commencer à accepter le trafic acheminé vers le nouveau nom de domaine. Pour terminer la création du domaine et le processus d'inscription, exécutez cette commande. 
  
```
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Cette commande ne renvoie aucun résultat, par conséquent, pour vérifier qu’elle a fonctionné, exécutez la commande suivante.
  
```
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Celle-ci renverra des résultats semblables à ce qui suit.
  
||||
|:-----|:-----|:-----|
| `Name` <br/> | `Status` <br/> | `Authentication` <br/> |
| `FQDN of new domain` <br/> | `Verified` <br/> | `Managed` <br/> |
   
## <a name="see-also"></a>Voir aussi

#### 

[Aide pour les partenaires](https://go.microsoft.com/fwlink/p/?LinkID=533477)
