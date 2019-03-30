---
title: Créer un groupe Office 365 avec un emplacement par défaut des données spécifique
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: ''
ms.collection: Strat_SP_gtc
localization_priority: Priority
description: Découvrez comment créer un groupe Office 365 avec un emplacement par défaut des données spécifique dans un environnement multigéographique.
ms.openlocfilehash: a46a34d9fd5be9b3acda5ee3859f4eed08797b7c
ms.sourcegitcommit: 8ba20f1b1839630a199585da0c83aaebd1ceb9fc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30933988"
---
# <a name="create-an-office-365-group-with-a-specific-pdl"></a><span data-ttu-id="3782f-103">Créer un groupe Office 365 avec un emplacement par défaut des données spécifique</span><span class="sxs-lookup"><span data-stu-id="3782f-103">Create an Office 365 Group with a specific PDL</span></span>

<span data-ttu-id="3782f-104">Quand un utilisateur dans un environnement multigéographique crée un groupe Office 365, l’emplacement par défaut des données du groupe est automatiquement défini sur celui de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3782f-104">When users in a multi-geo environment create an Office 365 Group, the group preferred data location is automatically set to that of the user.</span></span> <span data-ttu-id="3782f-105">Si vous devez créer un groupe avec un emplacement par défaut des données spécifique, vous le pouvez en utilisant la cmdlet Microsoft PowerShell New-UnifiedGroup d’Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3782f-105">If you need to create a group with a specific PDL, you can do that using the Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet.</span></span> <span data-ttu-id="3782f-106">Lorsque vous procédez de la sorte, la boîte aux lettres de groupe et le site SharePoint associé à celui-ci sont approvisionnés dans l’emplacement par défaut des données spécifié.</span><span class="sxs-lookup"><span data-stu-id="3782f-106">When you do this, both the group mailbox and SharePoint site associated with the group will be provisioned in the specified PDL.</span></span>

<span data-ttu-id="3782f-107">Pour faire cela, vous devez être un administrateur général ou un administrateur SharePoint Online ou Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3782f-107">You must be a global administrator or a SharePoint Online or Exchange Online administrator to do this.</span></span>

<span data-ttu-id="3782f-108">Pour créer un groupe Office 365 avec l’emplacement par défaut des données que vous spécifiez, connectez-vous à Exchange Online PowerShell en transmettant le paramètre *-MailBoxRegion* avec le code d’emplacement géographique.</span><span class="sxs-lookup"><span data-stu-id="3782f-108">To create an Office 365 Group with the PDL that you specify, connect to Exchange Online PowerShell and pass the parameter *-MailBoxRegion* with the geo location code.</span></span>

<span data-ttu-id="3782f-109">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="3782f-109">For example:</span></span> 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Capture d’écran de la cmdlet PowerShell New-UnifiedGroup avec la syntaxe](media/multi-geo-new-group-with-pdl-powershell.png)

<span data-ttu-id="3782f-111">Notez que l’approvisionnement du site du groupe SharePoint est à la demande.</span><span class="sxs-lookup"><span data-stu-id="3782f-111">Note that SharePoint group site provisioning is on-demand.</span></span> <span data-ttu-id="3782f-112">Le site est approvisionné la première fois qu’un propriétaire ou un membre du groupe tente d’y accéder.</span><span class="sxs-lookup"><span data-stu-id="3782f-112">The site will be provisioned the first time a group owner or member attempts to access it.</span></span>

## <a name="geo-location-codes"></a><span data-ttu-id="3782f-113">Codes d’emplacement géographique</span><span class="sxs-lookup"><span data-stu-id="3782f-113">Geo location codes</span></span>

[!INCLUDE [Office 365 Multi-Geo locations](includes/office-365-multi-geo-locations.md)]

## <a name="see-also"></a><span data-ttu-id="3782f-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3782f-114">See also</span></span>

[<span data-ttu-id="3782f-115">Connexion à Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="3782f-115">Connect to Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)