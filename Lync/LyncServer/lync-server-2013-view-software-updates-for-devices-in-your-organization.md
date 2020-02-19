---
title: 'Lync Server 2013 : affichage des mises à jour logicielles pour les appareils de votre organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7926c9c10ba30ed4683b1e05d6e22c4b817f502c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="40821-102">Affichage des mises à jour logicielles pour les périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40821-102">View software updates for devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40821-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="40821-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="40821-104">Avec Lync Server 2013, vous utilisez le service Web de mise à jour des périphériques pour afficher et gérer les mises à jour logicielles des appareils de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="40821-104">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="40821-105">Ces mises à jour sont disponibles dans les fichiers. cab (armoire) à partir du site Web [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)du support technique de Microsoft à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="40821-105">These updates are available in .cab (cabinet) files from the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="40821-106">Après avoir téléchargé le fichier. cab, exécutez l’applet de commande **Import-CSDeviceUpdate** pour importer les règles de mise à jour des périphériques à partir du fichier. cab.</span><span class="sxs-lookup"><span data-stu-id="40821-106">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="40821-107">Pour plus d’informations sur l’applet de commande **Import-CSDeviceUpdate** , voir [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="40821-107">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="40821-108">Avant de déployer une nouvelle mise à jour dans votre entreprise, vérifiez qu’elle fonctionne correctement sur un périphérique de test.</span><span class="sxs-lookup"><span data-stu-id="40821-108">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="40821-109">Pour afficher les mises à jour logicielles des périphériques de communications unifiées</span><span class="sxs-lookup"><span data-stu-id="40821-109">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="40821-110">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="40821-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="40821-111">À partir du site Web du [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)support technique de Microsoft à l’adresse, téléchargez le fichier. cab vers un emplacement sur un ordinateur Lync Server\\2013 (par\\exemple, C : updates UCUpdates. cab).</span><span class="sxs-lookup"><span data-stu-id="40821-111">From the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="40821-112">Importez les règles de mise à jour\\des périphériques à\\partir du fichier C : updates UCUpdates. cab en exécutant l’une des applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="40821-112">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="40821-113">Si le fichier .cab se trouve sur le même ordinateur que celui qui exécute le service à mettre à jour (service:Redmond-websvc-2), exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="40821-113">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="40821-114">Si le fichier .cab se trouve sur un autre ordinateur que celui qui exécute le service à mettre à jour (service:Redmond-websvc-3), exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="40821-114">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="40821-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40821-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="40821-116">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="40821-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="40821-117">Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Mise à jour du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="40821-117">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="40821-118">Dans la page **Mise à jour du périphérique**, cliquez sur une mise à jour de la liste, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="40821-118">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="40821-p103">**Annulez une mise à jour en attente.** Pour empêcher le déploiement de la mise à jour sélectionnée vers les périphériques de votre entreprise, cliquez sur le menu **Action**, puis sur **Annuler les mises à jour en attente**.</span><span class="sxs-lookup"><span data-stu-id="40821-p103">**Cancel a pending update.** To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="40821-p104">**Approuvez une mise à jour.** Pour autoriser le déploiement de la mise à jour sélectionnée vers les périphériques de votre entreprise, cliquez sur le menu **Action**, puis sur **Approuver**.</span><span class="sxs-lookup"><span data-stu-id="40821-p104">**Approve an update.** To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="40821-p105">**Restaurez une mise à jour.** Pour autoriser le déploiement d’une mise à jour approuvée vers les périphériques de votre entreprise, cliquez sur le menu **Action**, puis sur **Restaurer**.</span><span class="sxs-lookup"><span data-stu-id="40821-p105">**Restore an update.** To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="40821-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40821-125">See Also</span></span>


[<span data-ttu-id="40821-126">Gestion des appareils, des téléphones et des applications clientes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40821-126">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

