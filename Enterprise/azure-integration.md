---
title: Intégration Azure avec Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 12/29/2016
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_O365
search.appverid:
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Votre abonnement à Office 365 comprend un abonnement Azure AD. Intégrer Office 365 avec Azure AD si vous souhaitez que la synchronisation de mot de passe ou authentification unique avec votre environnement local.
ms.openlocfilehash: abeda5eb915ac4ff9e395ab3b28f1e0cb7a68163
ms.sourcegitcommit: 92d16c0926e4be3fd493fe9b4eb317fb54996bca
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/31/2018
ms.locfileid: "21550078"
---
# <a name="azure-integration-with-office-365"></a><span data-ttu-id="1567b-104">Intégration Azure avec Office 365</span><span class="sxs-lookup"><span data-stu-id="1567b-104">Azure integration with Office 365</span></span>

<span data-ttu-id="1567b-p102">Office 365 utilise Azure Active Directory (AD Azure) pour gérer les identités des utilisateurs en arrière-plan. Votre abonnement à Office 365 comprend un abonnement gratuit à Azure AD afin que vous pouvez intégrer Office 365 avec Azure AD si vous souhaitez synchroniser les mots de passe ou configuration de l’authentification unique avec votre environnement local. Vous pouvez également acheter des fonctionnalités avancées pour mieux gérer vos comptes.</span><span class="sxs-lookup"><span data-stu-id="1567b-p102">Office 365 uses Azure Active Directory (Azure AD)to manage user identities behind the scenes. Your Office 365 subscription includes a free subscription to Azure AD so that you can integrate Office 365 with Azure AD if you want to sync passwords or set up single sign-on with your on-premises environment. You can also buy advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="1567b-108">Azure offre également d’autres fonctionnalités, telles que la gestion des applications intégrées, que vous pouvez utiliser pour étendre et personnaliser vos abonnements Office 365.</span><span class="sxs-lookup"><span data-stu-id="1567b-108">Azure also offers other functionality, like managing integrated apps, that you can use to extend and customize your Office 365 subscriptions.</span></span>
  
<span data-ttu-id="1567b-109">Vous pouvez également utiliser les conseillers Azure AD : le [Gestionnaire d’Azure AD se connecter](https://aka.ms/aadconnectpwsync), le [Gestionnaire de déploiement d’AD FS](https://aka.ms/adfsguidance), l' [Assistant de Deploymnet Azure RMS](https://aka.ms/azuremsguidance)et le [guide de configuration Azure AD Premium](https://aka.ms/aadpguidance).</span><span class="sxs-lookup"><span data-stu-id="1567b-109">You can also use the Azure AD advisors: the [Azure AD Connect advisor](https://aka.ms/aadconnectpwsync), the [AD FS deployment advisor](https://aka.ms/adfsguidance), the [Azure RMS Deploymnet Wizard](https://aka.ms/azuremsguidance), and the [Azure AD Premium setup guide](https://aka.ms/aadpguidance).</span></span>
  
## <a name="azure-ad-editions-and-office-365-identity-management"></a><span data-ttu-id="1567b-110">Azure AD éditions et pour la gestion des identités Office 365</span><span class="sxs-lookup"><span data-stu-id="1567b-110">Azure AD editions and Office 365 identity management</span></span>

<span data-ttu-id="1567b-p103">Si vous disposez d’un abonnement payant à Office 365, vous avez également un abonnement gratuit à Azure AD. Vous pouvez utiliser Azure AD pour créer et gérer des comptes d’utilisateur et groupe. Pour activer cet abonnement, que vous devez effectuer un enregistrement unique. Ensuite, vous pouvez accéder Azure AD à partir de votre portail d’administration d’Office 365. Pour plus d’informations, voir [inscrire votre libre abonnement Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=617127).</span><span class="sxs-lookup"><span data-stu-id="1567b-p103">If you have a paid subscription to Office 365, you also have a free subscription to Azure AD. You can use Azure AD to create and manage user and group accounts. To activate this subscription you have to complete a one-time registration. Afterward, you can access Azure AD from your Office 365 admin portal. For instructions, see [register your free Azure AD subscription](https://go.microsoft.com/fwlink/p/?LinkId=617127).</span></span> 
  
> [!TIP]
> <span data-ttu-id="1567b-p104">Suivez les instructions ci-dessus pour abonnement register Azure AD gratuit qui est fourni avec votre abonnement à Office 365. N’accédez directement à Azure.Microsoft.com pour vous inscrire ou vous finirez avec un abonnement d’essai ou payant à Microsoft Azure séparé de votre un gratuite pour Office 365.</span><span class="sxs-lookup"><span data-stu-id="1567b-p104">Follow the instructions above to register the free Azure AD subscription that comes with your subscription to Office 365. Don't go directly to Azure.Microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free one for Office 365.</span></span> 
  
<span data-ttu-id="1567b-118">Avec l’abonnement gratuit que vous pouvez synchroniser avec les annuaires locaux, configuration de l’authentification unique et synchroniser avec le logiciel de nombreux comme les applications de service, telles que force de vente, échange et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="1567b-118">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox and many more.</span></span>
  
<span data-ttu-id="1567b-p105">Si vous souhaitez que des fonctionnalités améliorées de domaine Active Directory, la synchronisation bidirectionnelle et autres fonctionnalités de gestion, vous pouvez mettre à niveau votre abonnement gratuit à un abonnement payant premium. Pour plus d’informations, consultez [éditions Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=524280).</span><span class="sxs-lookup"><span data-stu-id="1567b-p105">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription. For details see [Azure Active Directory editions](https://go.microsoft.com/fwlink/p/?LinkId=524280).</span></span>
  
<span data-ttu-id="1567b-121">Pour plus d’informations sur Office 365 et Azure AD, voir [identités Office 365 et Azure Active Directory](https://support.office.com/article/06a189e7-5ec6-4af2-94bf-a22ea225a7a9).</span><span class="sxs-lookup"><span data-stu-id="1567b-121">For more information about Office 365 and Azure AD, see [Understanding Office 365 Identity and Azure Active Directory](https://support.office.com/article/06a189e7-5ec6-4af2-94bf-a22ea225a7a9).</span></span>
  
## <a name="extend-the-capabilities-of-your-office-365-tenant"></a><span data-ttu-id="1567b-122">Étendre les fonctionnalités de votre client Office 365</span><span class="sxs-lookup"><span data-stu-id="1567b-122">Extend the capabilities of your Office 365 tenant</span></span>

|<span data-ttu-id="1567b-123">**Fonctionnalité**</span><span class="sxs-lookup"><span data-stu-id="1567b-123">**Feature**</span></span>|<span data-ttu-id="1567b-124">**Description**</span><span class="sxs-lookup"><span data-stu-id="1567b-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1567b-125">Applications intégrées</span><span class="sxs-lookup"><span data-stu-id="1567b-125">Integrated apps</span></span>  <br/> |<span data-ttu-id="1567b-p106">Vous pouvez accorder l’accès des applications spécifiques à vos données d’Office 365, tels que la messagerie, calendriers, contacts, les utilisateurs, groupes, fichiers et dossiers. Vous pouvez également autoriser ces applications de niveau administrateur global et les rendre disponibles pour votre ensemble de l’entreprise en enregistrant les applications dans Azure AD. Pour plus d’informations, consultez [applications intégrée et Azure AD pour les administrateurs Office 365](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a).</span><span class="sxs-lookup"><span data-stu-id="1567b-p106">You can grant individual apps access to your Office 365 data, like mail, calendars, contacts, users, groups, files, and folders. You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD. For details see [Integrated Apps and Azure AD for Office 365 administrators](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a).  </span></span><br/> <span data-ttu-id="1567b-129">Voir aussi [Galerie d’applications Azure AD et single-sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="1567b-129">See also [Azure AD application gallery and single-sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="1567b-130">PowerApps</span><span class="sxs-lookup"><span data-stu-id="1567b-130">PowerApps</span></span>  <br/> | <span data-ttu-id="1567b-p107">Power applications sont les applications ciblées pour les appareils mobiles qui peuvent se connecter à vos données sources telles que des listes SharePoint et les autres applications de données. Pour plus d’informations, voir [créer un PowerApp pour obtenir la liste dans SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) et la [page PowerApps](https://powerapps.microsoft.com/) .</span><span class="sxs-lookup"><span data-stu-id="1567b-p107">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists, and other data apps. See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and [PowerApps page](https://powerapps.microsoft.com/) for details.  </span></span><br/> |
   
<span data-ttu-id="1567b-133">Pour d’autres ressources sur le Cloud Microsoft et Office 365, consultez les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="1567b-133">For other resources about the Microsoft Cloud and Office 365, see these resources:</span></span>
  
- [<span data-ttu-id="1567b-134">Identité cloud Microsoft pour les architectes d’entreprise</span><span class="sxs-lookup"><span data-stu-id="1567b-134">Microsoft Cloud Identity for Enterprise Architects</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=828642)
    
- [<span data-ttu-id="1567b-135">Déployer la synchronisation d’annuaires (DirSync) Office 365 dans Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="1567b-135">Deploy Office 365 Directory Synchronization (DirSync) in Microsoft Azure</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517887)
    
