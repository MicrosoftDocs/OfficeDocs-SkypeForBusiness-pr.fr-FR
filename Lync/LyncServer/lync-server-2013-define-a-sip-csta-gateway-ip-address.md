---
title: 'Lync Server 2013 : Définition d’une adresse IP de passerelle SIP/CSTA'
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
ms.openlocfilehash: c50958f2c7c44045e25ff4ac9619f3ad73a5f302
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="abaa6-102">Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abaa6-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abaa6-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="abaa6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="abaa6-104">Si Lync Server se connecte à la passerelle SIP/CSTA déployée pour le contrôle d’appel distant à l’aide d’une connexion TCP (Transmission Control Protocol), vous devez définir l’adresse IP de la passerelle dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="abaa6-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="abaa6-105">Cette étape n’est pas nécessaire pour les passerelles qui prennent en charge les connexions TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="abaa6-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="abaa6-106">Pour toute passerelle qui prend en charge les connexions TLS, vous pouvez ignorer cette procédure et poursuivre le déploiement du contrôle d’appel distant en suivant les étapes décrites dans l’article [permettre aux utilisateurs de Lync pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="abaa6-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="abaa6-107">Pour définir l’adresse IP de la passerelle SIP/CSTA à l’aide du générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="abaa6-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="abaa6-108">Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="abaa6-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="abaa6-109">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="abaa6-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="abaa6-110">Sélectionnez l’option de téléchargement d’une topologie existante.</span><span class="sxs-lookup"><span data-stu-id="abaa6-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="abaa6-111">Développez le nœud **serveurs d’applications de confiance** .</span><span class="sxs-lookup"><span data-stu-id="abaa6-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="abaa6-112">Cliquez avec le bouton droit sur le pool d’applications approuvé que vous avez créé, comme décrit dans [la rubrique Configurer une entrée d’application fiable pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="abaa6-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="abaa6-113">Décochez la case **activer la réplication des données de configuration pour ce pool** .</span><span class="sxs-lookup"><span data-stu-id="abaa6-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="abaa6-114">Cliquez sur **limiter l’utilisation du service aux adresses IP sélectionnées**.</span><span class="sxs-lookup"><span data-stu-id="abaa6-114">Click **Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="abaa6-115">Le paramètre par défaut est **utiliser toutes les adresses IP configurées**.</span><span class="sxs-lookup"><span data-stu-id="abaa6-115">The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="abaa6-116">Dans la zone de texte **adresse IP principale** , entrez l’adresse IP de la passerelle SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="abaa6-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="abaa6-117">Pour mettre à jour la topologie dans le magasin central de gestion, dans l’arborescence de la console, cliquez sur **Lync Server**, puis, dans le volet **actions** , cliquez sur **publier**.</span><span class="sxs-lookup"><span data-stu-id="abaa6-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="abaa6-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="abaa6-118">See Also</span></span>


[<span data-ttu-id="abaa6-119">Configuration d’un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abaa6-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="abaa6-120">Configuration d’une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abaa6-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

