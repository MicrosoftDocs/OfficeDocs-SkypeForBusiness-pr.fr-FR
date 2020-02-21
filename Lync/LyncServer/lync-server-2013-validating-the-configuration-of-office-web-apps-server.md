---
title: 'Lync Server 2013 : validation de la configuration d’Office Web Apps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068c3fcfd33668918eb330b64d816ceca818de27
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="dedf2-102">Validation de la configuration d’Office Web Apps Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dedf2-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dedf2-103">_**Dernière modification de la rubrique :** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="dedf2-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="dedf2-104">Une fois qu’Office Web Apps Server a été ajouté à la topologie et une fois la topologie publiée, vous devez voir deux nouveaux événements de journal des événements dans le journal des événements Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dedf2-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="dedf2-105">Tout d’abord, un événement de MCU de données LS (ID d’événement 41034) doit être ajouté ; Cet événement signale que le serveur Office Web Apps a été découvert :</span><span class="sxs-lookup"><span data-stu-id="dedf2-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="dedf2-106">**Le serveur de conférence Web Office Web Apps Server est découvert, le contenu PowerPoint est activé.**</span><span class="sxs-lookup"><span data-stu-id="dedf2-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="dedf2-p102">En plus de cela, un autre événement LS Data MCU devrait être affiché (ID d’événement 41032), retournant les URL du serveur Office Web Apps. Par exemple, vous devriez voir un message semblable à :</span><span class="sxs-lookup"><span data-stu-id="dedf2-p102">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>

<span data-ttu-id="dedf2-109">**Serveur de conférence Web la découverte d’Office Web Apps Server a réussi.**</span><span class="sxs-lookup"><span data-stu-id="dedf2-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="dedf2-110">**Page du présentateur interne Office Web Apps Server :https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="dedf2-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="dedf2-111">**Page du participant interne Office Web Apps Server :https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="dedf2-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="dedf2-112">**Page du présentateur externe Office Web Apps Server :https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="dedf2-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="dedf2-113">**Page du participant interne Office Web Apps Server :https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="dedf2-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="dedf2-114">Si un événement LS Data MCU ayant l’ID d’événement 41033 s’affiche, cela signifie que la découverte d’Office Web Apps Server na pas fonctionné.</span><span class="sxs-lookup"><span data-stu-id="dedf2-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="dedf2-115">Dans ce cas, Microsoft Lync Server 2013 essaiera autant de fois que nécessaire pour découvrir le serveur Office Web Apps nouvellement configuré.</span><span class="sxs-lookup"><span data-stu-id="dedf2-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="dedf2-116">Si le processus de découverte ne fonctionne pas à chaque essai, nous vous conseillons de supprimer Office Web Apps Server de votre document de topologie, de publier la topologie mise à niveau, puis d’essayer de rajouter Office Web Apps Server à votre topologie une fois les problèmes de topologie résolus.</span><span class="sxs-lookup"><span data-stu-id="dedf2-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="dedf2-117">Si Office Web Apps Server semble être configuré correctement et qu’il a été reconnu par le processus de découverte, vous pouvez vérifier qu’Office Web Apps Server fonctionne comme prévu en partageant une présentation PowerPoint entre deux clients Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="dedf2-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="dedf2-118">Si l’utilisateur A peut charger et afficher la présentation PowerPoint et si l’utilisateur B peut ensuite rejoindre la réunion et consulter la présentation, alors Office Web Apps Server fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="dedf2-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="dedf2-p105">Même si Office Web Apps Server semble être configuré correctement, il est possible que le message d’erreur suivant s’affiche : « Certaines fonctionnalités de partage ne sont pas disponibles en raison de problèmes de connectivité de serveur » lorsque vous essayez de partager une présentation PowerPoint. Si vous recevez ce message d’erreur, vous devez redémarrer le ou les serveurs frontaux associés à la nouvelle configuration d’Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="dedf2-p105">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation. If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

