---
title: Expanseur des paramètres du pool de serveurs Edge
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Pour modifier les paramètres d’un pool Edge de serveur unique ou de serveurs multiples, vous disposez des sections suivantes :'
ms.openlocfilehash: 642e71aed428326140dd72646426f833c8d760b7
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19964582"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="b87aa-103">Expanseur des paramètres du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="b87aa-103">Edge Settings Expander</span></span>
 
<span data-ttu-id="b87aa-104">Pour modifier les paramètres d’un pool Edge de serveur unique ou de serveurs multiples, vous disposez des sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="b87aa-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="b87aa-105">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="b87aa-105">General settings</span></span>
    
- <span data-ttu-id="b87aa-106">Paramètres de sélection du tronçon suivant</span><span class="sxs-lookup"><span data-stu-id="b87aa-106">Next hop selection settings</span></span>
    
- <span data-ttu-id="b87aa-107">Configuration du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b87aa-107">Edge Server configuration</span></span>
    
## 

### <a name="general-settings"></a><span data-ttu-id="b87aa-108">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="b87aa-108">General settings</span></span>

<span data-ttu-id="b87aa-p101">Nom de domaine complet (FQDN) du pool interne pour le pool de serveurs Edge. Modifiez le nom de domaine complet du pool pour changer ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="b87aa-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>
  
<span data-ttu-id="b87aa-111">Activez la case à cocher **Activer la fédération pour ce pool Edge (Port 5061)** si vous configurez une fédération avec un serveur Lync Server 2013, partenaire de confiance Microsoft Lync Server 2010 ou Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b87aa-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Lync Server 2013, Microsoft Lync Server 2010 or Microsoft Office Communications Server 2007 R2 trusted partner.</span></span>
  
<span data-ttu-id="b87aa-112">Sélectionnez **Activer la fédération XMPP pour ce pool Edge** pour activer la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="b87aa-112">Select **Enable XMPP federation for this Edge pool** to enable XMPP federation.</span></span>
  
<span data-ttu-id="b87aa-113">Spécifiez le numéro de port pour **Port de réplication de configuration interne (HTTPS)**.</span><span class="sxs-lookup"><span data-stu-id="b87aa-113">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>
  
### <a name="next-hop-selection-settings"></a><span data-ttu-id="b87aa-114">Paramètres de sélection du tronçon suivant</span><span class="sxs-lookup"><span data-stu-id="b87aa-114">Next hop selection settings</span></span>

<span data-ttu-id="b87aa-115">Pour configurer ou modifier le **pool du tronçon suivant** utilisé par les serveurs Edge pour communiquer avec l’infrastructure interne, sélectionnez un directeur, un pool directeur, un serveur frontal ou un pool de serveurs frontaux dans la zone de liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="b87aa-115">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="b87aa-116">Seules les directeurs ou frontaux qui ont été configurés dans le Générateur de topologie s’affiche pour la sélection.</span><span class="sxs-lookup"><span data-stu-id="b87aa-116">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>
  
### <a name="edge-server-configuration"></a><span data-ttu-id="b87aa-117">Configuration du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b87aa-117">Edge Server configuration</span></span>

<span data-ttu-id="b87aa-118">Pour modifier ou spécifier des paramètres pour les **paramètres externes** des serveurs Edge, vous devez déterminer si vous allez utiliser des adresses IP distinctes pour l’accès SIP, la conférence web et le service audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="b87aa-118">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>
  
<span data-ttu-id="b87aa-p103">Si vous envisagez d’utiliser des adresses IP distinctes chaque fois, activez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Un enregistrement d’hôte DNS (A) doit avoir été créé pour chaque service.</span><span class="sxs-lookup"><span data-stu-id="b87aa-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>
  
<span data-ttu-id="b87aa-p104">Pour chaque service externe, vous spécifiez un nom de domaine complet et un port associé. Par exemple, l’**accès SIP** utilise SIP.contoso.com avec le port 5061 associé.</span><span class="sxs-lookup"><span data-stu-id="b87aa-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b87aa-p105">Si vous sélectionnez des noms de domaine complets distincts pour chaque service externe, chacun de ces services doit être associé à une valeur de port unique. Par défaut, le SIP utilise le port 5061/TLS, le service Edge de conférence web, le port 444/TLS et le serveur de conférence A/V, le port 443/TLS. Si vous apportez des modifications à l’un de ces paramètres, y compris en utilisant un nom de domaine complet et des adresses IP ou des ports distincts, vous devez mettre à jour tous les autres services qui dépendent de valeurs configurées initialement.</span><span class="sxs-lookup"><span data-stu-id="b87aa-p105">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span> 
  
<span data-ttu-id="b87aa-p106">Si vous déterminez que votre organisation utilisera un nom de domaine complet et une adresse IP uniques pour les services côté externe, désactivez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Vous pouvez ensuite modifier les valeurs du nom de domaine complet du pool et du port **Accès SIP**, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b87aa-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b87aa-128">Si vous apportez des modifications à l’un de ces paramètres, y compris en utilisant un nom de domaine complet et des adresses IP ou des ports distincts, vous devez mettre à jour tous les autres services qui dépendent des valeurs configurées initialement.</span><span class="sxs-lookup"><span data-stu-id="b87aa-128">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span> 
  
### 

<span data-ttu-id="b87aa-129">Pour plus d’informations sur la définition et la configuration des paramètres des Services Edge, voir [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="b87aa-129">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>
  

