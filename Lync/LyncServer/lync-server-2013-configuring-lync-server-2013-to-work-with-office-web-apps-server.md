---
title: Configuration de Lync Server 2013 pour qu’il fonctionne avec Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2043c974654ba2a65b3d831cd65fef420e4b5708
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a><span data-ttu-id="6767d-102">Configuration de Lync Server 2013 pour qu’il fonctionne avec Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="6767d-102">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6767d-103">_**Dernière modification de la rubrique :** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="6767d-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="6767d-104">Pour pouvoir configurer Lync Server 2013 afin d’utiliser Office Web Apps Server, Office Web Apps Server doit être déployé et configuré.</span><span class="sxs-lookup"><span data-stu-id="6767d-104">Before you can configure Lync Server 2013 to use Office Web Apps Server, Office Web Apps Server must be deployed and configured.</span></span> <span data-ttu-id="6767d-105">Voir le document **Guide de déploiement d’Office Web Apps Server et d’Office Web Apps** pour obtenir des informations détaillées sur la façon d’installer et de configurer un serveur Office Web Apps unique ou pour obtenir des informations sur la façon d’installer et de configurer une batterie de serveurs Office Web Apps Server en vue d’une haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="6767d-105">See the document **Guide to Deploying Office Web Apps Server and Office Web Apps** for detail information on how to install and configure a single Office Web Apps Server, or for information on how to install and configure an Office Web Apps Server Farm for high availability.</span></span>

<span data-ttu-id="6767d-106">Une fois l’installation d’Office Web Apps Server correctement effectuée et la configuration correcte de votre batterie de serveurs Web, vous devez configurer Lync Server pour qu’il communique avec le nouveau serveur ; pour ce faire, vous devez ajouter l’URL de découverte d’Office Web Apps Server à votre topologie Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6767d-106">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Lync Server to communicate with the new server; this is done by adding the Office Web Apps Server discovery URL to your Lync Server topology.</span></span> <span data-ttu-id="6767d-107">Pour ajouter le serveur Office Web Apps Server à votre topologie, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6767d-107">To add Office Web Apps Server to your topology, complete the following steps:</span></span>

1.  <span data-ttu-id="6767d-108">Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologies Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6767d-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="6767d-109">Dans la boîte de dialogue **Générateur de topologie**, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6767d-109">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="6767d-p103">Dans la boîte de dialogue **Enregistrer la topologie sous**, tapez le nom de votre document de topologie (par exemple, **PreWebAppsServerTopology**) dans la zone **Nom du fichier**, puis cliquez sur **Enregistrer**. Vous pouvez par la suite récupérer et republier cette topologie si vous rencontrez des problèmes avec votre nouvelle topologie.</span><span class="sxs-lookup"><span data-stu-id="6767d-p103">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>

4.  <span data-ttu-id="6767d-112">Dans le générateur de topologies, développez **Lync Server 2013**, développez le nom de votre site, développez **Pools frontaux Enterprise Edition**, cliquez avec le bouton droit sur le nom de l’un de vos pools, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6767d-112">In Topology Builder, expand **Lync Server 2013**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>

5.  <span data-ttu-id="6767d-113">Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, recherchez l’en-tête **Serveur Office Web Apps associé**, puis cliquez sur **Nouveau** (ou sélectionnez un serveur Office Web Apps Server existant dans la liste déroulante).</span><span class="sxs-lookup"><span data-stu-id="6767d-113">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

6.  <span data-ttu-id="6767d-114">Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre ordinateur Office Web Apps Server dans la zone **Nom de domaine complet du serveur Office Web Apps**. L’URL de découverte du serveur Office Web Apps Server est alors automatiquement entrée dans la zone **URL de découverte du serveur Office Web Apps**.</span><span class="sxs-lookup"><span data-stu-id="6767d-114">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="6767d-115">Si Office Web Apps Server est installé sur site et dans la même zone de réseau que Lync Server 2013, l’option le **serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)** ne doit pas être sélectionné.</span><span class="sxs-lookup"><span data-stu-id="6767d-115">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="6767d-116">Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez alors l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)**.</span><span class="sxs-lookup"><span data-stu-id="6767d-116">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>

7.  <span data-ttu-id="6767d-p104">Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, cliquez sur **OK**. Ensuite, cliquez sur **OK** dans la boîte de dialogue **Modifier les propriétés**. L’URL de découverte d’Office Web Apps doit alors figurer parmi les associations du pool.</span><span class="sxs-lookup"><span data-stu-id="6767d-p104">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box. The Office Web Apps discovery URL will then be listed as one of the pool's Associations.</span></span>

<span data-ttu-id="6767d-119">Vous devez répéter ce processus pour chaque pool à associer à votre serveur Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="6767d-119">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>

<span data-ttu-id="6767d-p105">Après avoir ajouté l’URL de découverte à la topologie, vous devez ensuite publier cette topologie mise à jour. Pour cela, dans le Générateur de topologie :</span><span class="sxs-lookup"><span data-stu-id="6767d-p105">After you have added the discovery URL to the topology you must then publish this updated topology. To do that in Topology Builder:</span></span>

1.  <span data-ttu-id="6767d-122">Cliquez sur **Action**, puis sur **Publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="6767d-122">Click **Action** and then click **Publish Topology**.</span></span>

2.  <span data-ttu-id="6767d-123">Dans l’Assistant Publication de la topologie, dans la page **Publier la topologie**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="6767d-123">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="6767d-124">Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="6767d-124">On the **Publishing wizard complete** page, click **Finish**.</span></span>

4.  <span data-ttu-id="6767d-125">Fermez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="6767d-125">Close Topology Builder.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

