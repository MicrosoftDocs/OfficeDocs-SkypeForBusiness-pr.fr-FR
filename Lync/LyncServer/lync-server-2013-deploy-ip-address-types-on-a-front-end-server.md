---
title: 'Lync Server 2013 : déploiement des types d’adresses IP sur un serveur frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3be24a05cf75adfc999205bb306010ba43fa1d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a><span data-ttu-id="71b65-102">Déployer des types d’adresses IP sur un serveur frontal pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71b65-102">Deploy IP address types on a Front End Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71b65-103">_**Dernière modification de la rubrique :** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="71b65-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="71b65-104">À l’aide du générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="71b65-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="71b65-105">Pour déployer des types d’adresses IP sur un serveur frontal</span><span class="sxs-lookup"><span data-stu-id="71b65-105">To deploy IP address types on a Front End Server</span></span>

1.  <span data-ttu-id="71b65-106">Sous **Pools frontaux Enterprise Edition**, cliquez avec le bouton droit sur le serveur d’un pool, puis sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="71b65-106">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="71b65-107">(Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**)</span><span class="sxs-lookup"><span data-stu-id="71b65-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="71b65-p102">Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. S’il s’agit d’une configuration double pile, sélectionnez **Activer IPv4** et **Activer IPv6**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="71b65-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="71b65-110">**Boîte de dialogue Modifier les propriétés du pool de serveurs frontaux**</span><span class="sxs-lookup"><span data-stu-id="71b65-110">**Edit Properties dialog box for the Front End Server pool**</span></span>
    
    <span data-ttu-id="71b65-111">![Boîte de dialogue Modifier les propriétés du serveur frontal](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Boîte de dialogue Modifier les propriétés du serveur frontal")</span><span class="sxs-lookup"><span data-stu-id="71b65-111">![Front End Server Edit Properties dialog box](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Front End Server Edit Properties dialog box")</span></span>
    
      - <span data-ttu-id="71b65-p103">**Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="71b65-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="71b65-114">Cette option est recommandée pour les configurations IP version 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="71b65-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="71b65-115">**Limiter l’utilisation des services aux adresses IP sélectionnées**</span><span class="sxs-lookup"><span data-stu-id="71b65-115">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="71b65-116">: sélectionnez cette option pour indiquer une adresse spécifique à utiliser sur le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="71b65-116">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="71b65-117">Si vous sélectionnez cette option, vous devez entrer une valeur pour **adresse IP principale**.</span><span class="sxs-lookup"><span data-stu-id="71b65-117">If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
      - <span data-ttu-id="71b65-p105">**Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (PSTN). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="71b65-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="71b65-121">**Adresse IP PSTN**</span><span class="sxs-lookup"><span data-stu-id="71b65-121">**PSTN IP address**.</span></span> <span data-ttu-id="71b65-122">L’installation de cartes d’interface réseau (NIC) supplémentaires pour prendre en charge la configuration de l’adresse IP RTC pour Lync Server 2013 n’est pas prise en charge sur les rôles de serveur de médiation colocalisés.</span><span class="sxs-lookup"><span data-stu-id="71b65-122">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="71b65-123">Pour plus d’informations sur les configurations NIC prises en charge pour Lync Server 2013, consultez la rubrique [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="71b65-123">For more information about supported NIC configurations for Lync Server 2013, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

