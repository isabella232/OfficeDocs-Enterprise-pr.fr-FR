---
title: "Afficher les licences et les services avec Office 365 PowerShell"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- DecEntMigration
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: "Explique comment utiliser Office 365 PowerShell pour afficher des informations sur les plans de licence, les services et les licences qui sont disponibles dans votre organisation d’Office 365."
ms.openlocfilehash: dc9ea5ad5077062a05c0070ffecbf580d3aacc49
ms.sourcegitcommit: d31cf57295e8f3d798ab971d405baf3bd3eb7a45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="view-licenses-and-services-with-office-365-powershell"></a>Afficher les licences et les services avec Office 365 PowerShell

**Résumé :** Explique comment utiliser Office 365 PowerShell pour afficher des informations sur les plans de licence, les services et les licences qui sont disponibles dans votre organisation d’Office 365.
  
Chaque abonnement à Office 365 se compose des éléments suivants :
- **Plans de gestion de licences** Il s’agit également de plans d’aslicense ou de plans d’Office 365. Plans de gestion des licences définissent les services Office 365 qui sont disponibles pour les utilisateurs. Votre abonnement à Office 365 peut contenir plusieurs plans de gestion des licences. Un plan de gestion des licences exemple serait E3 d’entreprise Office 365.
    
- **Services** Ce sont également les plans asservice connus. Les services sont les produits Office 365, les fonctionnalités et les fonctionnalités qui sont disponibles dans chaque plan de gestion des licences, par exemple, Exchange Online et Office Professionnel Plus. Les utilisateurs peuvent avoir plusieurs licences de différents plans de gestion des licences qui accordent l’accès à des services différents.
    
- **Licences** Chaque plan de licences contient le nombre de licences que vous avez acheté. Vous attribuez des licences aux utilisateurs afin de pouvoir utiliser les services Office 365 qui sont définies par le plan de gestion des licences. Chaque compte d’utilisateur requiert au moins une licence à partir d’un plan de gestion des licences pour pouvoir se connecter à Office 365 et utiliser les services.
    
Vous pouvez utiliser Office 365 PowerShell pour afficher plus d’informations sur les plans de gestion des licences disponibles, les licences et les services de votre organisation d’Office 365. Pour plus d’informations sur les produits, les fonctionnalités et les services qui sont disponibles dans les différentes souscriptions d’Office 365, reportez-vous à la section [Options du Plan Office 365](https://go.microsoft.com/fwlink/p/?LinkId=691147).
## <a name="before-you-begin"></a>Avant de commencer
<a name="RTT"> </a>

- Les procédures décrites dans cette rubrique exigent une connexion à Office 365 PowerShell. Pour plus d'informations, reportez-vous à [Se connecter à Office 365 PowerShell](connect-to-office-365-powershell.md).
    
- Un script PowerShell est disponible qui automatise les procédures décrites dans cette rubrique. Plus précisément, le script vous permet d’afficher et de désactiver des services dans votre organisation d’Office 365, y compris de balancement. Pour plus d’informations, consultez [désactiver l’accès à balancement avec Office 365 PowerShell](disable-access-to-sway-with-office-365-powershell.md).
    
## <a name="view-information-about-licensing-plans-and-the-available-licenses"></a>Afficher les informations sur les plans de licence et sur les licences disponibles
<a name="ShortVersion"> </a>

Pour afficher des informations récapitulatives sur vos plans de gestion des licences en cours et les licences disponibles pour chaque plan, exécutez la commande suivante dans Office 365 PowerShell :
  
```
Get-MsolAccountSku
```

Les résultats contiennent les informations suivantes :
  
- **AccountSkuId :** Afficher les plans de gestion des licences disponibles pour votre organisation à l’aide de la syntaxe `<CompanyName>:<LicensingPlan>`.  _<CompanyName>_ est la valeur que vous avez fournies lorsque vous inscrit à Office 365 et êtes unique pour votre organisation. Le _<LicensingPlan>_ valeur est la même pour tout le monde. Par exemple, dans la valeur de `litwareinc:ENTERPRISEPACK`, le nom de la société est `litwareinc`et le nom du plan licence `ENTERPRISEPACK`, qui est le nom de système pour Office 365 entreprise E3.
    
- **ActiveUnits :** Nombre de licences que vous avez des achats pour un plan de gestion des licences spécifique.
    
- **WarningUnits :** Nombre de licences d’un plan de gestion des licences que vous n’avez pas renouvelé et qui expire après la période de grâce de 30 jours.
    
- **ConsumedUnits :** Nombre de licences que vous avez affectés aux utilisateurs à partir d’un plan de gestion des licences spécifique.
    
Pour plus d’informations sur les services Office 365 qui sont disponibles dans l’ensemble de vos modes de licence, exécutez la commande suivante :
  
```
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

Le tableau suivant montre les plans de service d’Office 365 et leurs noms conviviaux pour les services les plus courants. La liste des plans de service peut-être être différente. Pour obtenir une liste complète des services offerts et leurs noms conviviaux, contactez le [Support de l’Office](https://support.office.com/home/contact).
  
|Plan de service ***|Description ***|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Office Professionnel Plus  <br/> |
| `MCOSTANDARD` <br/> |Skype Entreprise Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office Online  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online Plan 2  <br/> |
   
Pour plus d’informations sur les services Office 365 qui sont disponibles dans un plan de gestion des licences spécifique, utilisez la syntaxe suivante.
  
```
(Get-MsolAccountSku | where {$_.AccountSkuId -eq " <AccountSkuId>"}).ServiceStatus
```

Cet exemple montre les services Office 365 qui sont disponibles dans le plan de gestion des licences litwareinc:ENTERPRISEPACK (Office 365 entreprise E3).
  
```
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="new-to-office-365"></a>Vous débutez avec Office 365 ?
<a name="ShortVersion"> </a>

||
|:-----|
|![L’icône court pour l’apprentissage de LinkedIn](images/d547e1cb-7c66-422b-85be-7e7db2a9cf97.png) **nouveau vers Office 365 ?**         Découvrez la vidéo gratuits pour les [professionnels de l’informatique et les administrateurs d’Office 365](https://support.office.com/article/Office-365-admin-and-IT-pro-courses-68cc9b95-0bdc-491e-a81f-ee70b3ec63c5), proposée par formation de LinkedIn. |
   
## <a name="see-also"></a>See also
<a name="ShortVersion"> </a>

#### 

[Afficher les utilisateurs avec ou sans licence avec Office 365 PowerShell](view-licensed-and-unlicensed-users-with-office-365-powershell.md)
  
[Afficher les détails de service et de licence de compte avec Office 365 PowerShell](view-account-license-and-service-details-with-office-365-powershell.md)
#### 

[Get-MsolAccountSku](https://go.microsoft.com/fwlink/p/?LinkId=691549)
