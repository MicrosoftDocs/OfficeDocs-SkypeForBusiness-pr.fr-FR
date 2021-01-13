---
title: Expanseur des paramètres des services web
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: À partir du Générateur de topologie, vous pouvez modifier les paramètres de port utilisés pour vos services web internes et externes. En outre, si vous déployez l’équilibrage de charge DNS (Domain Name System), vous pouvez utiliser le Générateur de topologie pour configurer le nom de domaine complet (FQDN) du pool qui se résout en adresses IP physiques de tous les serveurs de ce pool.
ms.openlocfilehash: 99f052ebbfc4199f077744eee444333822075c24
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800694"
---
# <a name="web-services-settings-expander"></a><span data-ttu-id="aac0b-104">Expandeur des paramètres des services web</span><span class="sxs-lookup"><span data-stu-id="aac0b-104">Web Services Settings Expander</span></span>
 
<span data-ttu-id="aac0b-105">À partir du Générateur de topologie, vous pouvez modifier les paramètres de port utilisés pour vos services web internes et externes.</span><span class="sxs-lookup"><span data-stu-id="aac0b-105">From within Topology Builder, you can modify the port settings used for both your internal and external web services.</span></span> <span data-ttu-id="aac0b-106">En outre, si vous déployez l’équilibrage de charge DNS (Domain Name System), vous pouvez utiliser le Générateur de topologie pour configurer le nom de domaine complet (FQDN) du pool qui se résout en adresses IP physiques de tous les serveurs de ce pool.</span><span class="sxs-lookup"><span data-stu-id="aac0b-106">In addition, and if you are deploying Domain Name System (DNS) load balancing, you can use Topology Builder to configure the fully qualified domain name (FQDN) of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span>
  
### <a name="editing-web-services-settings"></a><span data-ttu-id="aac0b-107">Modification des paramètres des services web</span><span class="sxs-lookup"><span data-stu-id="aac0b-107">Editing Web Services Settings</span></span>

1. <span data-ttu-id="aac0b-108">Sélectionnez le serveur frontal Standard Edition ou le pool frontal Enterprise Edition approprié, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="aac0b-108">Select the appropriate Standard Edition Front End Server or the appropriate Enterprise Edition Front End Pool, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="aac0b-109">Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur l’onglet **Services web**.</span><span class="sxs-lookup"><span data-stu-id="aac0b-109">In the **Edit Properties** dialog box, click the **Web services** tab.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="aac0b-110">Si vous avez plusieurs serveurs frontaux ou serveurs frontaux, le FQDN des services Web externes doit être unique.</span><span class="sxs-lookup"><span data-stu-id="aac0b-110">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="aac0b-111">Par exemple, si vous définissez le nom de groupe des services Web externes d’un serveur frontal en tant que **pool01.contoso.com,** vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="aac0b-111">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="aac0b-112">Si vous déployez également des directeurs, le FQDN des services Web externes défini pour n’importe quel directeur ou pool directeur doit être unique à partir de tout autre directeur ou pool directeur, ainsi que de tout pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="aac0b-112">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="aac0b-113">Si vous décidez de remplacer les services web internes par un FQDN auto-défini, chaque FQDN doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.</span><span class="sxs-lookup"><span data-stu-id="aac0b-113">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
3. <span data-ttu-id="aac0b-114">Si vous modifiez les propriétés d’un pool Enterprise Edition, vous avez la possibilité de choisir **Remplacer le nom de domaine complet**.</span><span class="sxs-lookup"><span data-stu-id="aac0b-114">If you are editing the properties of an Enterprise Edition pool, you have the option to select **Override FQDN**.</span></span> <span data-ttu-id="aac0b-115">Ne sélectionnez cette option que si vous utilisez l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="aac0b-115">This option should be selected only if you are using Domain Name System (DNS) load balancing.</span></span> <span data-ttu-id="aac0b-116">Si vous utilisez l’équilibrage de la charge DNS, sélectionnez **Remplacer le nom de domaine complet**, puis dans la zone de texte, tapez le nom de domaine complet du pool qui est résolu en adresses IP physiques de tous les serveurs de ce pool.</span><span class="sxs-lookup"><span data-stu-id="aac0b-116">If you are using DNS load balancing, select **Override FQDN** and then, in the text box, type the FQDN of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span> <span data-ttu-id="aac0b-117">Si vous n’utilisez pas l’équilibrage de la charge DNS, et si vous n’avez pas sélectionné **Remplacer le nom de domaine complet**, vous ne pouvez pas modifier le nom de domaine complet des services web internes.</span><span class="sxs-lookup"><span data-stu-id="aac0b-117">If you are not using DNS load balancing, and if you do not select **Override FQDN**, you cannot change the Internal web services FQDN.</span></span> <span data-ttu-id="aac0b-118">Le FQDN des services web internes est l’URL utilisée par les utilisateurs internes pour se connecter à Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="aac0b-118">The Internal web services FQDN is the URL used by internal users to connect to Skype for Business Server.</span></span>
    
4. <span data-ttu-id="aac0b-p105">Vous pouvez aussi entrer de nouvelles valeurs HTTP, HTTPS ou HTTP et HTTPS pour les **Ports d’écoute** et les **Ports publiés**. Les ports d’écoute sont les ports utilisés par les services Internet (IIS) pour écouter le trafic SIP (Session Initiation Protocol) entrant ; les ports publiés sont des ports configurés sur un programme d’équilibrage de la charge ou un serveur proxy inverse et sont également utilisés pour écouter le trafic SIP entrant. Par défaut, les ports d’écoute et publiés HTTP sont définis sur le port 80 ; les ports HTTPS correspondants sont tous deux définis sur 443. La valeur par défaut pour les deux ports publiés HTTP est 8080 et les ports HTTPS correspondants sont définis sur 4443.</span><span class="sxs-lookup"><span data-stu-id="aac0b-p105">Optionally, enter new HTTP, HTTPS, or HTTP and HTTPS values for the **Listening ports** and the **Published ports**. Listening ports are the ports used by Internet Information Services (IIS) to listen for incoming Session Initiation Protocol (SIP) traffic; published ports are ports configured on a load balancer or reverse proxy server and are also used to listen for incoming SIP traffic. By default, both the HTTP listening port and the HTTP published port are set to port 80; the corresponding HTTPS ports are both set to 443. The default value for the two HTTP published ports is 8080 and the corresponding HTTPS ports are set to 4443.</span></span>
    
5. <span data-ttu-id="aac0b-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="aac0b-123">Click **OK**.</span></span>
    
<span data-ttu-id="aac0b-124">Si vous modifiez le nom de domaine complet interne ou l’un des ports d’écoute assignés, vous devez réexécuter l’installation locale sur tous les serveurs du pool pour que ces modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="aac0b-124">If you modify either the internal FQDN or any of the listening port assignments, you must local setup again on all the servers in the pool in order to have those changes take effect.</span></span>
  

