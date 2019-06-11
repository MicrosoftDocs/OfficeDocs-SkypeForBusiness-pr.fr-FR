---
title: 'Lync Server 2013: vérification de la configuration d’Office Web Apps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35844ae2ae73937d6840e480dc57393b91d13eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="bbc6b-102">Validation de la configuration d’Office Web Apps Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbc6b-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbc6b-103">_**Dernière modification de la rubrique:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="bbc6b-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="bbc6b-104">Une fois qu’Office Web Apps Server a été ajouté à la topologie et après la publication de cette topologie, vous devriez voir deux nouveaux événements du journal des événements dans le journal des événements de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bbc6b-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="bbc6b-105">D’abord, un événement LS Data MCU (ID d’événement 41034) devrait être ajouté, cet événement va signaler la découverte du serveur Office Web Apps :</span><span class="sxs-lookup"><span data-stu-id="bbc6b-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="bbc6b-106">**Le serveur de conférence Web Office Web Apps Server est découvert, le contenu PowerPoint est activé.**</span><span class="sxs-lookup"><span data-stu-id="bbc6b-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="bbc6b-p102">En plus de cela, un autre événement LS Data MCU devrait être affiché (ID d’événement 41032), retournant les URL du serveur Office Web Apps. Par exemple, vous devriez voir un message semblable à :</span><span class="sxs-lookup"><span data-stu-id="bbc6b-p102">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>

<span data-ttu-id="bbc6b-109">**La découverte du serveur de conférence Web Office Web Apps Server a réussi.**</span><span class="sxs-lookup"><span data-stu-id="bbc6b-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="bbc6b-110">**Page de présentateur interne d’Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="bbc6b-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="bbc6b-111">**Page Office Web Apps Server en interne:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="bbc6b-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="bbc6b-112">**Page de présentateur externe d’Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="bbc6b-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="bbc6b-113">**Page Office Web Apps Server en interne:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="bbc6b-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="bbc6b-114">Si vous voyez un événement MCU de données LS avec l’ID d’événement de 41033 qui signifie que la découverte d’Office Web Apps Server a échoué.</span><span class="sxs-lookup"><span data-stu-id="bbc6b-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="bbc6b-115">Dans ce cas, Microsoft Lync Server 2013 essaie autant de fois que nécessaire pour découvrir le serveur Office Web Apps que vous venez de configurer.</span><span class="sxs-lookup"><span data-stu-id="bbc6b-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="bbc6b-116">Si le processus de découverte échoue à plusieurs reprises, il est recommandé de supprimer Office Web Apps Server de votre document topologique, de publier la topologie mise à jour, puis de réessayer d’ajouter Office Web Apps Server à la topologie suite à la résolution des problèmes de connectivité.</span><span class="sxs-lookup"><span data-stu-id="bbc6b-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="bbc6b-117">Si Office Web Apps Server semble correctement configuré et a été reconnu par le processus de découverte, vous pouvez vérifier qu’Office Web Apps Server fonctionne comme prévu en partageant une présentation PowerPoint entre deux clients Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="bbc6b-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="bbc6b-118">Si l’utilisateur A peut charger et afficher la présentation PowerPoint et s’il peut rejoindre la réunion et voir cette présentation, Office Web Apps Server fonctionne.</span><span class="sxs-lookup"><span data-stu-id="bbc6b-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="bbc6b-119">Même si Office Web Apps Server semble correctement configuré, vous pouvez recevoir le message d’erreur «certaines fonctionnalités de partage ne sont pas disponibles en raison de problèmes de connectivité du serveur» lorsque vous essayez de partager une présentation PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="bbc6b-119">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="bbc6b-120">Si vous recevez ce message d’erreur, vous devez redémarrer le ou les serveurs frontaux associés au nouveau serveur Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="bbc6b-120">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

