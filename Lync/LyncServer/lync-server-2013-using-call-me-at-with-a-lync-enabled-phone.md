---
title: 'Lync Server 2013 : utilisation de m’appeler à l’aide d’un téléphone compatible Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 840089b2e65e158086d33f8ebfdfc6828e4e9317
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535821"
---
# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="2de04-102">Utilisation de m’appeler à l’aide d’un téléphone compatible Lync et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2de04-102">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2de04-103">_**Dernière modification de la rubrique :** 2013-08-09_</span><span class="sxs-lookup"><span data-stu-id="2de04-103">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="2de04-104">La fonctionnalité m’appeler dans Lync permet aux utilisateurs de rejoindre la partie audio d’une conférence à l’aide d’un téléphone cellulaire, d’une ligne fixe ou d’un autre appareil connecté au réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="2de04-104">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="2de04-105">Lorsque vous tentez de participer à une réunion à l’aide de Lync, vous verrez généralement apparaître la boîte de dialogue **audio joindre une réunion** :</span><span class="sxs-lookup"><span data-stu-id="2de04-105">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="2de04-106">![Capture d’écran de la capture de la fenêtre audio de la réunion](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Capture d’écran de la capture de la fenêtre audio de la réunion")</span><span class="sxs-lookup"><span data-stu-id="2de04-106">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="2de04-107">Si vous sélectionnez **m’appeler au**, vous pouvez choisir un numéro de téléphone dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="2de04-107">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="2de04-108">Lync Server 2013 passe un appel téléphonique au numéro sélectionné et vous pouvez ensuite utiliser ce téléphone pour participer à la partie audio de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="2de04-108">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="2de04-109">La liste déroulante est complétée par les numéros de téléphone (pour le téléphone mobile, téléphone personnel ou autre téléphone) que vous avez entrés sous l’onglet **téléphones** de la boîte de dialogue **Lync-options** :</span><span class="sxs-lookup"><span data-stu-id="2de04-109">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="2de04-110">![Capture d’écran des options de configuration des téléphones Lync](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Capture d’écran des options de configuration des téléphones Lync")</span><span class="sxs-lookup"><span data-stu-id="2de04-110">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="2de04-111">Si vous n’avez pas entré de numéros de téléphone dans l’onglet **téléphones** , aucun numéro n’est disponible dans la zone de liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="2de04-111">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="2de04-112">Toutefois, vous pouvez toujours cliquer sur **nouveau numéro** et faire en sorte que Lync Server compose le numéro de votre choix :</span><span class="sxs-lookup"><span data-stu-id="2de04-112">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="2de04-113">![Capture d’écran de la fenêtre Lync Join Meeting audio Calling](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Capture d’écran de la fenêtre Lync Join Meeting audio Calling")</span><span class="sxs-lookup"><span data-stu-id="2de04-113">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="2de04-114">La fonctionnalité m’appeler sur fonctionne extrêmement bien si vous l’utilisez dans la mesure où elle a été conçue : en faisant appel à Lync Server pour appeler un numéro de téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="2de04-114">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="2de04-115">Toutefois, vous pouvez rencontrer une expérience moins efficace que si vous demandez à Lync Server de vous appeler auprès d’un point de terminaison compatible Lync (par exemple, un téléphone dans une salle de conférence).</span><span class="sxs-lookup"><span data-stu-id="2de04-115">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="2de04-116">Vous trouverez ci-dessous le problème que vous pouvez rencontrer, ainsi que deux façons de contourner le problème.</span><span class="sxs-lookup"><span data-stu-id="2de04-116">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="2de04-117">Pour commencer, voici ce qui se passe lorsque vous fournissez la fonctionnalité me contacter avec le numéro de téléphone d’un téléphone compatible Lync.</span><span class="sxs-lookup"><span data-stu-id="2de04-117">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="2de04-118">Supposons que Ken Myer tente de participer à une réunion en faisant appel à Lync Server de la part de 1-206-555-1219, un numéro de téléphone compatible Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2de04-118">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="2de04-119">Ken est initialement connecté à la réunion, mais après quelques secondes, l’appel du message **n’a pas abouti ou s’est terminé**, et Ken a été supprimé de la réunion :</span><span class="sxs-lookup"><span data-stu-id="2de04-119">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="2de04-120">![Capture d’écran de la fenêtre Conférence d’appels Lync](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Capture d’écran de la fenêtre Conférence d’appels Lync")</span><span class="sxs-lookup"><span data-stu-id="2de04-120">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="2de04-121">Notez cependant qu’il existe une incohérence dans la fenêtre de conversation Lync.</span><span class="sxs-lookup"><span data-stu-id="2de04-121">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="2de04-122">Ken Myer est le seul nom figurant sous l’en-tête **participants** .</span><span class="sxs-lookup"><span data-stu-id="2de04-122">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="2de04-123">Toutefois, si vous regardez dans la barre de titre de la fenêtre, vous verrez que la conférence contient au total 4 participants.</span><span class="sxs-lookup"><span data-stu-id="2de04-123">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="2de04-124">De même, si vous regardez dans la fenêtre de conversation de l’un des autres participants de la Conférence, vous ne verrez pas Ken Myer dans la section :</span><span class="sxs-lookup"><span data-stu-id="2de04-124">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="2de04-125">![Capture d’écran de la fenêtre Liste des participants Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Capture d’écran de la fenêtre Liste des participants Lync")</span><span class="sxs-lookup"><span data-stu-id="2de04-125">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="2de04-126">En même temps, Ken Myer pourra participer à la partie audio de l’appel à l’aide de son téléphone compatible Lync.</span><span class="sxs-lookup"><span data-stu-id="2de04-126">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="2de04-127">La fonctionnalité m’appeler sur a réellement fonctionné, mais l’expérience utilisateur n’est pas optimale.</span><span class="sxs-lookup"><span data-stu-id="2de04-127">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="2de04-128">Il existe au moins deux façons de contourner ce problème.</span><span class="sxs-lookup"><span data-stu-id="2de04-128">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="2de04-129">Si vous avez déjà rejoint une conférence de cette manière (par exemple, Ken Myer), vous pouvez généralement résoudre le problème en effectuant une autre modalité.</span><span class="sxs-lookup"><span data-stu-id="2de04-129">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="2de04-130">Par exemple, si vous envoyez un message instantané, la fenêtre de conversation affiche désormais tous les participants à la Conférence, y compris vous-même :</span><span class="sxs-lookup"><span data-stu-id="2de04-130">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="2de04-131">![Capture d’écran de la liste des participants et conversations Lync](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Capture d’écran de la liste des participants et conversations Lync")</span><span class="sxs-lookup"><span data-stu-id="2de04-131">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="2de04-132">À ce stade, vous devriez être en mesure de participer à la réunion de la manière attendue.</span><span class="sxs-lookup"><span data-stu-id="2de04-132">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="2de04-133">Vous pouvez également éviter ce problème en modifiant la façon dont vous rejoignez la réunion.</span><span class="sxs-lookup"><span data-stu-id="2de04-133">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="2de04-134">Si vous devez faire en sorte que Lync Server appelle un téléphone compatible Lync Server, vous devez commencer par rejoindre la réunion sans connexion audio.</span><span class="sxs-lookup"><span data-stu-id="2de04-134">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="2de04-135">Pour ce faire, sélectionnez ne pas participer au signal audio lorsque vous y êtes invité dans la boîte de dialogue audio joindre la réunion :</span><span class="sxs-lookup"><span data-stu-id="2de04-135">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="2de04-136">![Capture d’écran de la fenêtre de l’audio de la réunion](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Capture d’écran de la fenêtre de l’audio de la réunion")</span><span class="sxs-lookup"><span data-stu-id="2de04-136">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="2de04-137">Une fois que vous avez réussi à vous connecter à la réunion, vous pouvez désormais « inviter » le téléphone compatible Lync Server à participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="2de04-137">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="2de04-138">Pour ce faire, placez le curseur de la souris sur l’icône contacts, puis cliquez sur **inviter d’autres personnes**:</span><span class="sxs-lookup"><span data-stu-id="2de04-138">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="2de04-139">![Capture d’écran de la fenêtre inviter d’autres participants sur Lync](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Capture d’écran de la fenêtre inviter d’autres participants sur Lync")</span><span class="sxs-lookup"><span data-stu-id="2de04-139">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="2de04-140">La boîte de dialogue **Envoyer un message instantané** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="2de04-140">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="2de04-141">Ignorez le titre de la boîte de dialogue (vous n’envoyez pas réellement un message instantané) et tapez le numéro de téléphone du téléphone compatible Lync :</span><span class="sxs-lookup"><span data-stu-id="2de04-141">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="2de04-142">![Capture d’écran de la boîte de dialogue Envoyer un message instantané](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Capture d’écran de la boîte de dialogue Envoyer un message instantané")</span><span class="sxs-lookup"><span data-stu-id="2de04-142">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="2de04-143">Une fois que vous avez cliqué sur **OK**, Lync Server appellera le numéro entré dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2de04-143">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="2de04-144">Une fois la connexion établie, vous bénéficierez de toutes les fonctionnalités audio via le téléphone compatible Lync et vous pourrez voir et interagir avec la liste complète des conférences.</span><span class="sxs-lookup"><span data-stu-id="2de04-144">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

