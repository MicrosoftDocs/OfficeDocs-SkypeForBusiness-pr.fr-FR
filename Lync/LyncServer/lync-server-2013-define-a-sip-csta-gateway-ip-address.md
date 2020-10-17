---
title: 'Lync Server 2013 : définition d’une adresse IP de passerelle SIP/CSTA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3a88aa2209617a93b0feebf7c1cc6d8cccd0cf7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516381"
---
# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="420aa-102">Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="420aa-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="420aa-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="420aa-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="420aa-104">Si Lync Server se connecte à la passerelle SIP/CSTA que vous avez déployée pour le contrôle d’appel distant à l’aide d’une connexion TCP (Transmission Control Protocol), vous devez définir l’adresse IP de la passerelle dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="420aa-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="420aa-105">Cette étape n’est pas nécessaire pour les passerelles qui prennent en charge les connexions TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="420aa-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="420aa-106">Pour toute passerelle qui prend en charge les connexions TLS, vous pouvez ignorer cette procédure et continuer le déploiement du contrôle d’appel distant en suivant les étapes de la procédure [activer les utilisateurs Lync pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="420aa-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="420aa-107">Pour définir l’adresse IP de la passerelle SIP/CSTA à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="420aa-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="420aa-108">Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="420aa-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="420aa-109">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="420aa-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="420aa-110">Choisissez l’option consistant à télécharger une topologie existante.</span><span class="sxs-lookup"><span data-stu-id="420aa-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="420aa-111">Développez le nœud **Serveurs d’applications approuvés**.</span><span class="sxs-lookup"><span data-stu-id="420aa-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="420aa-112">Cliquez avec le bouton droit sur le pool d’applications approuvées que vous avez créé, comme décrit dans [Configure a Trusted application Entry for Remote Call Control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="420aa-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="420aa-113">Désactivez la case à cocher **Activer la réplication des données de configuration sur ce pool**.</span><span class="sxs-lookup"><span data-stu-id="420aa-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="420aa-p102">Cliquez sur **Limiter l’utilisation des services aux adresses IP sélectionnées**. Le paramètre par défaut est **Utiliser toutes les adresses IP configurées**.</span><span class="sxs-lookup"><span data-stu-id="420aa-p102">Click **Limit service usage to selected IP addresses**. The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="420aa-116">Dans la zone de texte **Adresse IP principale**, entrez l’adresse IP de la passerelle SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="420aa-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="420aa-117">Pour mettre à jour la topologie dans le magasin central de gestion, dans l’arborescence de la console, cliquez sur **Lync Server**, puis, dans le volet **Actions**, cliquez sur **Publier**.</span><span class="sxs-lookup"><span data-stu-id="420aa-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="420aa-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="420aa-118">See Also</span></span>


[<span data-ttu-id="420aa-119">Configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="420aa-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="420aa-120">Configurer une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="420aa-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

