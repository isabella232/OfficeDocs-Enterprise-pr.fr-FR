---
title: URL et plages d’adresses IP Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 8/13/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 'Résumé : Office 365 nécessite une connexion à Internet. Les points de terminaison ci-dessous doivent être accessibles pour les clients utilisant des plans Office 365, y compris GCC (Government Community Cloud).'
hideEdit: true
ms.openlocfilehash: 2e6f5afd097aa85c09847b58fd3166961116b773
ms.sourcegitcommit: 69d60723e611f3c973a6d6779722aa9da77f647f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/27/2018
ms.locfileid: "22540632"
---
# <a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="a762f-104">URL et plages d’adresses IP Office 365</span><span class="sxs-lookup"><span data-stu-id="a762f-104">Office 365 URLs and IP address ranges</span></span>

 <span data-ttu-id="a762f-p102">**Résumé :** Office 365 nécessite une connexion à Internet. Les points de terminaison ci-dessous doivent être accessibles pour les clients utilisant des plans Office 365, y compris GCC (Government Community Cloud).</span><span class="sxs-lookup"><span data-stu-id="a762f-p102">**Summary:** Office 365 requires connectivity to the Internet. The endpoints below should be reachable for customers using Office 365 plans, including Government Community Cloud (GCC).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a762f-p103">Microsoft développe un service web basé sur REST pour les entrées d’adresse IP et de FQDN sur cette page. Ce nouveau service vous permettra de configurer et mettre à jour des périphériques de périmètre de réseau tels que des pare-feu et serveurs proxy. Vous pouvez télécharger la liste des points de terminaison, la version actuelle de la liste ou modifications spécifiques. Ce service remplacera finalement le document XML dont le lien est sur cette page. Pour essayer ce nouveau service, accédez au [service web](managing-office-365-endpoints.md#webservice).</span><span class="sxs-lookup"><span data-stu-id="a762f-p103">Microsoft is developing a REST-based web service for the IP address and FQDN entries on this page. This new service will help you configure and update network perimeter devices such as firewalls and proxy servers. You can download the list of endpoints, the current version of the list, or specific changes. This service will eventually replace the XML document linked from this page. To try out this new service, go to [Web service](managing-office-365-endpoints.md#webservice).</span></span> 
  
<span data-ttu-id="a762f-112">*Office 365 dans le monde (GCC inclus)* | [Office 365 géré par 21Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](office-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](office-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](office-365-u-s-government-gcc-high-endpoints.md) |</span><span class="sxs-lookup"><span data-stu-id="a762f-112">*Office 365 Worldwide (+GCC)* | [Office 365 operated by 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](office-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](office-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](office-365-u-s-government-gcc-high-endpoints.md) |</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="a762f-113">**Dernière mise à jour :** 1/8/2018 -![RSS](media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Abonnement au journal des modifications](https://go.microsoft.com/fwlink/p/?linkid=236301)</span><span class="sxs-lookup"><span data-stu-id="a762f-113">**Last updated:** 8/1/2018 - ![RSS](media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Change Log subscription](https://go.microsoft.com/fwlink/p/?linkid=236301)</span></span> <br/> |<span data-ttu-id="a762f-114">**Téléchargement :** toutes les destinations obligatoires et facultatives dans une liste [XML](https://go.microsoft.com/fwlink/?LinkId=533185).</span><span class="sxs-lookup"><span data-stu-id="a762f-114">**Download:** all required and optional destinations in one [XML formatted](https://go.microsoft.com/fwlink/?LinkId=533185) list.</span></span>  <br/> | <span data-ttu-id="a762f-115">**Utilisation :** nos [fichiers PAC](managing-office-365-endpoints.md#pacfiles) proxy</span><span class="sxs-lookup"><span data-stu-id="a762f-115">**Use:** our proxy [PAC files](managing-office-365-endpoints.md#pacfiles)</span></span> <br/> |
   
 <span data-ttu-id="a762f-p104">Commencez avec la [gestion des points de terminaison Office 365](managing-office-365-endpoints.md) afin de comprendre nos recommandations pour gérer la connectivité réseau à l’aide de ces données. Les données de points de terminaison sont mises à jour au début de chaque mois avec de nouvelles adresses IP et URL publiées 30 jours avant d’être activées. Cela permet aux clients qui n’ont pas encore de mises à jour automatisées de terminer leurs processus avant qu’une nouvelle connectivité soit requise. Les points de terminaison peuvent également être mis à jour au cours du mois si besoin pour les demandes du support d’adresse, les incidents de sécurité ou autres exigences opérationnelles immédiates. Les données contenues sur la page ci-dessous sont générées à partir des services web REST. Si vous utilisez un script ou un périphérique réseau pour accéder à ces données, vous devez accéder directement au [service web](managing-office-365-endpoints.md#webservice).</span><span class="sxs-lookup"><span data-stu-id="a762f-p104">Start with [Managing Office 365 endpoints](managing-office-365-endpoints.md) to understand our recommendations for managing network connectivity using this data. Endpoints data is updated at the beginning of each month with new IP Addresses and URLs published 30 days in advance of being active. This allows for customers who do not yet have automated updates to complete their processes before new connectivity is required. Endpoints may also be updated during the month if needed to address support escalations, security incidents, or other immediate operational requirements. The data shown on this page below is all generated from the REST-based web services. If you are using a script or a network device to access this data, you should go to the [Web service](managing-office-365-endpoints.md#webservice) directly.</span></span>

<span data-ttu-id="a762f-p105">Les données de point de terminaison ci-dessous répertorient les exigences de connectivité à partir de l’ordinateur d’un utilisateur vers Office 365. Elles n’incluent pas les connexions réseau de Microsoft vers un réseau client, parfois appelées connexions réseau entrantes ou hybrides.</span><span class="sxs-lookup"><span data-stu-id="a762f-p105">Endpoint data below lists requirements for connectivity from a user’s machine to Office 365. It does not include network connections from Microsoft into a customer network, sometimes called hybrid or inbound network connections.</span></span>

<span data-ttu-id="a762f-p106">Les points de terminaison sont regroupés en quatre zones de service. Les trois premières zones de service peuvent être sélectionnées indépendamment pour la connectivité. La quatrième zone de service est une dépendance courante (appelée Microsoft 365 Common et Office Online) et doit toujours avoir une connectivité réseau.</span><span class="sxs-lookup"><span data-stu-id="a762f-p106">The endpoints are grouped into four service areas. The first three service areas can be independently selected for connectivity. The fourth service area is a common dependency (called Microsoft 365 Common and Office Online) and must always have network connectivity.</span></span>

<span data-ttu-id="a762f-127">Les colonnes de données affichées sont :</span><span class="sxs-lookup"><span data-stu-id="a762f-127">Data columns shown are:</span></span>

- <span data-ttu-id="a762f-p107">**ID** : numéro d’identification de la ligne, également connu sous forme d’un ensemble de points de terminaison. Cet ID est le même que celui retourné par le service web pour l’ensemble de points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="a762f-p107">**ID**: The ID number of the row, also known as an endpoint set. This ID is the same as is returned by the web service for the endpoint set.</span></span>

- <span data-ttu-id="a762f-p108">**Catégorie** : indique si l’ensemble de points de terminaison est associé à la classe « Optimiser », « Autoriser » ou « Par défaut ». Des informations sur ces catégories et des instructions pour les gérer sont disponibles dans la rubrique [http://aka.ms/pnc](http://aka.ms/pnc). Cette colonne répertorie également les ensembles de points de terminaison nécessaires pour que la connectivité réseau fonctionne. Pour les ensembles de points de terminaison qui ne nécessitent pas de connectivité réseau, nous fournissons des remarques dans ce champ pour indiquer les fonctionnalités manquantes si l’ensemble de points de terminaison est bloqué. Si vous excluez l’ensemble d’une zone de service, les ensembles de points de terminaison répertoriés comme requis ne nécessitent pas de connectivité.</span><span class="sxs-lookup"><span data-stu-id="a762f-p108">**Category**: Shows whether the endpoint set is categorized as “Optimize”, “Allow”, or “Default”. You can read about these categories and guidance for management of them at [http://aka.ms/pnc](http://aka.ms/pnc). This column also lists which endpoint sets are required to have network connectivity. For endpoint sets which are not required to have network connectivity, we provide notes in this field to indicate what functionality would be missing if the endpoint set is blocked. If you are excluding an entire service area, the endpoint sets listed as required do not require connectivity.</span></span>

- <span data-ttu-id="a762f-p109">**ER** : cette option est définie sur **Oui** si l’ensemble de points de terminaison est pris en charge sur Azure ExpressRoute avec des préfixes d’itinéraire Office 365. La Communauté BGP qui inclut les préfixes d’itinéraire indiqués s’aligne avec la zone de service répertoriée. Quand ER est défini sur **Non**, cela signifie qu’ExpressRoute n’est pas pris en charge pour cet ensemble de points de terminaison. Toutefois, le fait qu’ER soit défini sur **Non** ne signifie pas pour autant qu’aucun itinéraire n’est proposé pour un ensemble de points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="a762f-p109">**ER**: This is **Yes** if the endpoint set is supported over Azure ExpressRoute with Office 365 route prefixes. The BGP community that includes the route prefixes shown aligns with the service area listed. When ER is **No**, this means that ExpressRoute is not supported for this endpoint set. However, it should not be assumed that no routes are advertised for an endpoint set where ER is **No**.</span></span>

- <span data-ttu-id="a762f-p110">**Adresses** : répertorie les noms de domaine complets ou noms de domaines génériques et plages d’adresses IP pour l’ensemble de points de terminaison. Notez qu’une plage d’adresses IP est au format CIDR et peut inclure plusieurs adresses IP individuelles dans le réseau spécifié.</span><span class="sxs-lookup"><span data-stu-id="a762f-p110">**Addresses**: Lists the FQDNs or wildcard domain names and IP Address ranges for the endpoint set. Note that an IP Address range is in CIDR format and may include many individual IP Addresses in the specified network.</span></span>
 
- <span data-ttu-id="a762f-p111">**Ports** : répertorie les ports TCP ou UDP associés aux adresses pour former le point de terminaison réseau. Vous remarquerez peut-être certains doublons dans les plages d’adresses IP lorsque plusieurs ports sont répertoriés.</span><span class="sxs-lookup"><span data-stu-id="a762f-p111">**Ports**: Lists the TCP or UDP ports that are combined with the Addresses to form the network endpoint. You may notice some duplication in IP Address ranges where there are different ports listed.</span></span>

[!INCLUDE [Office 365 worldwide endpoints](./includes/office-365-worldwide-endpoints.md)]

## <a name="related-topics"></a><span data-ttu-id="a762f-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a762f-143">Related Topics</span></span>

[<span data-ttu-id="a762f-144">Gestion des points de terminaison Office 365</span><span class="sxs-lookup"><span data-stu-id="a762f-144">Office 365 Germany endpoints</span></span>](managing-office-365-endpoints.md)
  
[<span data-ttu-id="a762f-145">Résolution des problèmes de connectivité Office 365</span><span class="sxs-lookup"><span data-stu-id="a762f-145">Office 365 connectivity limits</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d.aspx)
  
[<span data-ttu-id="a762f-146">Connectivité des clients</span><span class="sxs-lookup"><span data-stu-id="a762f-146">Client connectivity</span></span>](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[<span data-ttu-id="a762f-147">Réseaux de distribution de contenu</span><span class="sxs-lookup"><span data-stu-id="a762f-147">Content delivery networks</span></span>](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[<span data-ttu-id="a762f-148">Plages d’adresses IP du centre de données Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="a762f-148">Microsoft Azure Datacenter IP Ranges</span></span>](https://www.microsoft.com/download/details.aspx?id=41653)
  
[<span data-ttu-id="a762f-149">Espace d’adresse IP public de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a762f-149">Microsoft Public IP Space</span></span>](https://www.microsoft.com/download/details.aspx?id=53602)
