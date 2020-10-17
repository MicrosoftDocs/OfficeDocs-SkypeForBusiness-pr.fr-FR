---
title: 'Lync Server 2013 : déploiement des types d’adresses IP sur un serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76dcde03d2a85eb45f7b2c28d6b7c7d99b41b20
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531481"
---
# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a><span data-ttu-id="5db55-102">Déployer des types d’adresses IP sur un serveur de médiation pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5db55-102">Deploy IP address types on a Mediation Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5db55-103">_**Dernière modification de la rubrique :** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="5db55-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="5db55-104">À l’aide du générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="5db55-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="5db55-105">Pour déployer des types d’adresses IP sur un serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="5db55-105">To deploy IP address types on a Mediation Server</span></span>

  - <span data-ttu-id="5db55-106">Dans le générateur de topologie, sous **pools de médiation**, cliquez avec le bouton droit sur le serveur dans un pool, puis sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5db55-106">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="5db55-107">(Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**)</span><span class="sxs-lookup"><span data-stu-id="5db55-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

  - <span data-ttu-id="5db55-p102">Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. S’il s’agit d’une configuration double pile, sélectionnez **Activer IPv4** et **Activer IPv6**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="5db55-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="5db55-110">**Boîte de dialogue Modifier les propriétés pour le pool de serveurs de médiation**</span><span class="sxs-lookup"><span data-stu-id="5db55-110">**Edit Properties dialog box for the Mediation Server pool**</span></span>
    
    <span data-ttu-id="5db55-111">![Page de propriétés générales de Lync Server avec nom de domaine complet](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Page de propriétés générales de Lync Server avec nom de domaine complet")</span><span class="sxs-lookup"><span data-stu-id="5db55-111">![Lync Server general properties page with FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server general properties page with FQDN")</span></span>
    
      - <span data-ttu-id="5db55-p103">**Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5db55-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5db55-114">Cette option est recommandée pour les configurations IP version 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="5db55-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="5db55-p104">**Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour indiquer une adresse spécifique à utiliser sur le nouveau serveur. Si vous sélectionnez cette option, vous devez entrer une valeur pour l’adresse IP principale.</span><span class="sxs-lookup"><span data-stu-id="5db55-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
      - <span data-ttu-id="5db55-p105">**Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (PSTN). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5db55-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="5db55-121">**Adresse IP PSTN**</span><span class="sxs-lookup"><span data-stu-id="5db55-121">**PSTN IP address**.</span></span> <span data-ttu-id="5db55-122">Définir une adresse IP PSTN lorsqu’un serveur de médiation est autonome.</span><span class="sxs-lookup"><span data-stu-id="5db55-122">Define a PSTN IP address when a Mediation Server is standalone.</span></span> <span data-ttu-id="5db55-123">Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5db55-123">This address must match the format of the selected address type.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5db55-124">L’installation de cartes d’interface réseau (NIC) supplémentaires pour prendre en charge la configuration de l’adresse IP RTC pour Lync Server 2013 n’est pas prise en charge sur les rôles de serveur de médiation colocalisés.</span><span class="sxs-lookup"><span data-stu-id="5db55-124">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="5db55-125">Pour plus d’informations sur les configurations NIC prises en charge pour Lync Server 2013, consultez la rubrique <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5db55-125">For more information about supported NIC configurations for Lync Server 2013, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

