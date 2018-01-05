---
title: "DirSync pour votre environnement de développement/test Office 365"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Ent_O365_Hybrid
- Ent_O365_Top
ms.custom:
- DecEntMigration
- Strat_O365_Enterprise
- TLG
- Ent_TLGs
ms.assetid: e6b27e25-74ae-4b54-9421-c8e911aef543
description: "Résumé : Configurer la synchronisation d’annuaire pour votre environnement de développement/test d’Office 365."
ms.openlocfilehash: da9a0070587c50ea9fc2f33612fb4885d6eaf695
ms.sourcegitcommit: d31cf57295e8f3d798ab971d405baf3bd3eb7a45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="dirsync-for-your-office-365-devtest-environment"></a>DirSync pour votre environnement de développement/test Office 365

 **Résumé :** Configurer la synchronisation d’annuaire pour votre environnement de développement/test d’Office 365.
  
De nombreuses organisations utilisent Azure AD Connect et la synchronisation d’annuaires (DirSync) pour synchroniser l’ensemble de comptes dans leur forêt de Windows Server Active Directory (AD) en local avec l’ensemble de comptes dans Office 365. Cet article explique comment vous pouvez ajouter DirSync avec synchronisation de mot de passe à l’environnement de développement/test Office 365, ce qui entraîne la configuration suivante.
  
![Environnement de développement/test d’Office 365 avec DirSync](images/be5b37b0-f832-4878-b153-436c31546e21.png)
  
Cette configuration se compose des éléments suivants :  
  
- Un abonnement d’évaluation Office 365 E5, qui arrive à expiration 30 jours après sa création.
    
- Un intranet d’organisation simplifié connecté à Internet, qui se compose de trois machines virtuelles sur un sous-réseau d’un réseau virtuel Azure (DC1, APP1 et CLIENT1). Azure AD Connect s’exécute sur APP1 pour synchroniser le domaine Windows Server AD avec Office 365.
    
Les deux phases de configuration de cet environnement de développement/test sont les suivantes :
  
1. Créez l’environnement de développement/test Office 365 (les machines virtuelles DC1, APP1 et CLIENT1 dans un réseau virtuel Azure avec un abonnement d’évaluation Office 365 E5).
    
2. Installez et configurez Azure AD Connect sur APP1.
    
> [!TIP]
> Cliquez [ici](http://aka.ms/catlgstack) pour une carte visuelle de tous les articles dans la pile d’un Guide de laboratoire de Test Microsoft Cloud.
  
## <a name="phase-1-create-an-office-365-devtest-environment"></a>Phase 1 : création d’un environnement de développement/test Office 365

Suivez les instructions affichées dans les étapes 1, 2 et 3 de l’article de [l’environnement de développement/test d’Office 365](office-365-dev-test-environment.md) . Voici la configuration obtenue.
  
![Environnement de développement/test Office 365](images/48fb91aa-09b0-4020-a496-a8253920c45d.png)
  
Cette configuration se compose des éléments suivants :  
  
- Un abonnement d’évaluation Office 365 E5.
    
- Un intranet d’organisation simplifié connecté à Internet, qui se compose des machines virtuelles DC1, APP1 et CLIENT1 sur un sous-réseau d’un réseau virtuel Azure.
    
## <a name="phase-2-install-azure-ad-connect-on-app1"></a>Phase 2 : installation d’Azure AD Connect sur APP1

Une fois installé et configuré, Azure AD Connect synchronise l’ensemble de comptes dans le domaine CORP Windows Server AD avec l’ensemble de comptes dans votre abonnement d’évaluation Office 365. La procédure suivante vous guide tout au long de l’installation d’Azure AD Connect sur APP1 et de la vérification de son fonctionnement.
  
### <a name="install-and-configure-azure-ad-connect-on-app1"></a>Installer et configurer Azure AD Connect dans APP1

1. Dans le [portail Azure](https://portal.azure.com), connectez-vous à APP1 avec le CORP\\compte utilisateur1.
    
2. À partir d’APP1, ouvrez une invite de commande Windows PowerShell de niveau administrateur, puis exécutez les commandes suivantes :
    
  ```
  Set-ItemProperty -Path "HKLM:\\SOFTWARE\\Microsoft\\Active Setup\\Installed Components\\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
Set-ItemProperty -Path "HKLM:\\SOFTWARE\\Microsoft\\Active Setup\\Installed Components\\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
Stop-Process -Name Explorer -Force

  ```

3. À partir de la barre des tâches, cliquez sur **Internet Explorer** et accédez à [https://aka.ms/aadconnect](https://aka.ms/aadconnect).
    
4. Sur la page Microsoft Azure Active Directory se connecter, cliquez sur **Télécharger**, puis cliquez sur **exécuter**.
    
5. Dans la page **Bienvenue dans Azure Connect d’Active Directory** , cliquez sur **J’accepte**, puis cliquez sur **Continuer**.
    
6. Dans la page **Paramètres Express** , cliquez sur **utiliser les paramètres express**.
    
7. Sur la page de **connexion à Azure AD** , tapez votre nom de compte administrateur global dans le type de **nom d’utilisateur,** son mot de passe **mot de passe**, puis cliquez sur **suivant**.
    
8. Sur la page de **connexion aux services AD DS** , tapez **CORP\\utilisateur1** dans **nom d’utilisateur,** tapez son mot de passe **mot de passe**, puis cliquez sur **suivant**.
    
9. Sur la page de **configuration de connexion AD Azure** , cliquez sur **Continuer sans vérifié tous les domaines**, puis cliquez sur **suivant**.
    
10. Sur la page **Prêt à configurer**, cliquez sur **Installer**.
    
11. Dans la page **Configuration terminée** , cliquez sur **Quitter**.
    
12. Dans Internet Explorer, accédez au portail Office 365 ([https://portal.office.com](https://portal.office.com)) et vous connecter à votre abonnement d’évaluation d’Office 365 avec votre compte d’administrateur global.
    
13. À partir de la page principale du portail, cliquez sur **Admin**.
    
14. Dans la navigation de gauche, cliquez sur **Utilisateurs > Utilisateurs actifs**.
    
    Notez le compte nommé **utilisateur1**. Ce compte est dans le domaine CORP Windows Server Active Directory et la preuve que la synchronisation d’annuaire a travaillé.
    
15. Cliquez sur le compte **d’utilisateur1** . Pour les licences de produit, cliquez sur **Modifier**.
    
16. Dans **les licences de produit**, sélectionnez votre pays, puis cliquez sur le contrôle **hors** d' **Office 365 entreprise E5** (commutation **on**). Cliquez sur **Enregistrer** en bas de la page, puis cliquez sur **Fermer**.
    
Voici la configuration obtenue.
  
![Environnement de développement/test d’Office 365 avec DirSync](images/be5b37b0-f832-4878-b153-436c31546e21.png)
  
Cette configuration se compose des éléments suivants :  
  
- Un abonnement d’évaluation Office 365 E5.
    
- Un intranet d’organisation simplifié connecté à Internet, qui se compose des machines virtuelles DC1, APP1 et CLIENT1 sur un sous-réseau d’un réseau virtuel Azure. Azure AD Connect s’exécute sur APP1 pour synchroniser le domaine CORP Windows Server AD avec Office 365 toutes les 30 minutes.
    
## <a name="next-step"></a>Étape suivante

Lorsque vous êtes prêt à déployer de synchronisation d’annuaire de votre organisation, voir [Déployer Office 365 synchronisation d’annuaires (DirSync) dans Microsoft Azure](deploy-office-365-directory-synchronization-dirsync-in-microsoft-azure.md).

## <a name="see-also"></a>See Also

[Guides de laboratoire de test d'adoption cloud](cloud-adoption-test-lab-guides-tlgs.md)
  
[Environnement de développement/test de configuration de base](base-configuration-dev-test-environment.md)
  
[Environnement de développement/test Office 365](office-365-dev-test-environment.md)
  
[Application du nuage sécurité pour votre environnement de développement/test d’Office 365](cloud-app-security-for-your-office-365-dev-test-environment.md)
  
[Avancées de protection contre les menaces pour votre environnement de développement/test d’Office 365](advanced-threat-protection-for-your-office-365-dev-test-environment.md)
  
[Adoption du cloud et solutions hybrides](cloud-adoption-and-hybrid-solutions.md)



