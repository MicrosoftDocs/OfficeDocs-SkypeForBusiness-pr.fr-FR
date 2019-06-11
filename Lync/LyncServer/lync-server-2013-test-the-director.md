---
title: 'Lync Server 2013 : Test du directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f889d548ddc9b177113aa3e395ac181095de8008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="42abe-102">Test du directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42abe-102">Test the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42abe-103">_**Dernière modification de la rubrique:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="42abe-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="42abe-104">À ce stade, un directeur ou un pool de réalisateur est configuré, mais les entrées SRV de votre système de noms de domaine (DNS) continuent à se connecter à l’aide d’un pool ou d’un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="42abe-104">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="42abe-105">Avant de modifier l’enregistrement DNS pour que les clients Lync 2013 se connectent automatiquement à l’aide du réalisateur, testez un client en le faisant manuellement au directeur.</span><span class="sxs-lookup"><span data-stu-id="42abe-105">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="42abe-106">Pour tester le déploiement</span><span class="sxs-lookup"><span data-stu-id="42abe-106">To test the deployment</span></span>

1.  <span data-ttu-id="42abe-107">Ouvrez une session sur l’ordinateur sur lequel est installé le panneau de configuration de Lync Server avec un compte de domaine faisant partie du groupe **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="42abe-107">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="42abe-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42abe-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="42abe-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="42abe-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="42abe-110">Dans le volet de navigation, cliquez sur **Topology**, puis, dans la colonne **statut** , vérifiez qu’il existe un serveur vert doté d’une flèche (c’est-à-dire, l’icône du serveur et l’icône du serveur de ![flèche verte](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "avec flèche verte")) pour votre directeur ou pool de réalisateur.</span><span class="sxs-lookup"><span data-stu-id="42abe-110">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="42abe-111">Connectez deux ordinateurs client sur lesquels le client Lync Server 2013 est installé, puis connectez-vous avec un autre compte d’utilisateur activé pour Lync Server 2013 sur chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="42abe-111">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="42abe-112">Sur l’un des ordinateurs clients, cliquez sur le menu **options** , sélectionnez le groupe paramètres **personnels** , cliquez sur **avancé**, sur **configuration manuelle**, puis définissez le **nom du serveur interne ou l’adresse IP** sur le nom complet. nom de domaine (FQDN) du nouveau directeur ou du pool de réalisateurs.</span><span class="sxs-lookup"><span data-stu-id="42abe-112">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="42abe-113">Ouvrez une session sur les deux clients et assurez-vous que le client qui se connecte à l’aide du directeur est en mesure de se connecter avec succès, d’afficher le statut de présence de l’autre utilisateur et de pouvoir échanger des messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="42abe-113">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

