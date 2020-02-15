---
title: 'Lync Server 2013 : considérations relatives à la migration pour les réunions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2657136b66675d08deb906879cb50962809f009c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="45d4e-102">Considérations relatives à la migration pour les réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45d4e-102">Migration considerations for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45d4e-103">_**Dernière modification de la rubrique :** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="45d4e-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="45d4e-104">Cette section aborde les sujets suivants :</span><span class="sxs-lookup"><span data-stu-id="45d4e-104">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="45d4e-105">Modifications apportées aux réunions dans Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45d4e-105">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="45d4e-106">Migration des utilisateurs en fonction de leurs besoins de conférence</span><span class="sxs-lookup"><span data-stu-id="45d4e-106">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="45d4e-107">Migration des réunions existantes et du contenu des réunions</span><span class="sxs-lookup"><span data-stu-id="45d4e-107">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="45d4e-108">Expérience utilisateur pendant la migration Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="45d4e-108">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="45d4e-109">Expérience utilisateur pendant la migration d’Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="45d4e-109">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="45d4e-110">Compatibilité de Microsoft Lync 2013 avec les réunions sur les versions précédentes du serveur</span><span class="sxs-lookup"><span data-stu-id="45d4e-110">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="45d4e-111">Modifications apportées aux réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45d4e-111">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="45d4e-112">**Fonctionnalités de Lync Server 2013.**    Lync Server 2013 fournit de nouvelles fonctionnalités de conférence qui deviennent accessibles aux utilisateurs une fois que leurs comptes sont déplacés vers lync Server 2013 et qu’ils se connectent avec le client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="45d4e-112">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="45d4e-113">De nouvelles fonctionnalités sont présentées dans la [nouvelle fonctionnalité de conférence de Lync server 2013](lync-server-2013-new-conferencing-features.md) et [les nouveautés pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="45d4e-113">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="45d4e-114">**URL de la réunion.**    Comme dans lync Server 2010, toutes les réunions nouvellement planifiées dans lync Server 2013 ont un préfixe d’URL https://et les réunions existantes sont migrées en même temps que les comptes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="45d4e-114">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="45d4e-115">Toutefois, Lync Server 2013 ne prend pas en charge l’appel de conférence Office Communications Server 2007 R2 (préfixe d’URL conf://) ou la conférence Web (préfixe d’URL meet://).</span><span class="sxs-lookup"><span data-stu-id="45d4e-115">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="45d4e-116">Pour plus d’informations, voir « Migrating meetings from Office Communications Server 2007 R2 » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="45d4e-116">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="45d4e-117">**Prise en charge du client.**    Contrairement à lync Server 2010, lync Server 2013 ne prend pas en charge les clients Office Communicator pour les conférences.</span><span class="sxs-lookup"><span data-stu-id="45d4e-117">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="45d4e-118">Vous ne pouvez pas utiliser les clients suivants pour participer à des réunions planifiées via le complément de réunion en ligne pour Lync 2013 :</span><span class="sxs-lookup"><span data-stu-id="45d4e-118">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="45d4e-119">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="45d4e-119">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="45d4e-120">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="45d4e-120">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="45d4e-121">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="45d4e-121">Office Communicator 2007</span></span>

  - <span data-ttu-id="45d4e-122">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="45d4e-122">Office Live Meeting 2007</span></span>

<span data-ttu-id="45d4e-123">Lors de la migration, les utilisateurs d’Office Communicator 2007 R2 doivent utiliser Lync Web App 2013 pour rejoindre les réunions Lync Server 2013 jusqu’à ce que leurs clients soient mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="45d4e-123">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="45d4e-124">Notez que les utilisateurs d’Office Communicator 2007 R2 peuvent continuer à utiliser leur client existant sur Lync Server 2013 pour les fonctionnalités de présence et de messagerie instantanée, mais pas les fonctionnalités de conférence non prises en charge.</span><span class="sxs-lookup"><span data-stu-id="45d4e-124">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="45d4e-125">Migration des utilisateurs en fonction de leurs besoins de conférence</span><span class="sxs-lookup"><span data-stu-id="45d4e-125">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="45d4e-126">**Organisateurs de réunions fréquents.**    Envisagez de migrer les organisateurs de réunions fréquents au début du processus afin qu’ils puissent tirer parti des nouvelles fonctionnalités lync Server 2013 et Lync 2013 décrites dans [nouvelles fonctionnalités de conférence dans Lync Server 2013](lync-server-2013-new-conferencing-features.md) et des nouveautés [pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="45d4e-126">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="45d4e-127">**Utilisateurs de Live Meeting.**    Si vous effectuez une migration à partir d’Office Communications Server 2007 R2 et que vous avez des utilisateurs qui ont besoin de fonctionnalités de conférence Web spécifiques à Live Meeting, en particulier la prise en charge de grandes réunions et de salles de sortie, vous disposez des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="45d4e-127">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="45d4e-128">Conseillez aux organisateurs d’utiliser le service Live Meeting, dans le cas où il est disponible dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="45d4e-128">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="45d4e-129">Laissez les organisateurs hébergés sur la version antérieure d’Office Communications Server, afin qu’ils puissent continuer à planifier des conférences Web Live Meeting basées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="45d4e-129">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="45d4e-130">Migration des réunions existantes et du contenu des réunions</span><span class="sxs-lookup"><span data-stu-id="45d4e-130">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="45d4e-131">Migration de réunions à partir de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="45d4e-131">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="45d4e-132">Lorsque vous déplacez un utilisateur de Lync Server 2010 vers Lync Server 2013, les informations suivantes se déplacent avec le compte de l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="45d4e-132">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="45d4e-133">Réunions déjà planifiées par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="45d4e-133">Meetings already scheduled by the user.</span></span> <span data-ttu-id="45d4e-134">Cela inclut les annuaires de conférence et les données de conférence.</span><span class="sxs-lookup"><span data-stu-id="45d4e-134">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="45d4e-135">Code confidentiel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="45d4e-135">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="45d4e-136">: le code confidentiel actuel de l’utilisateur fonctionne jusqu’à ce qu’il expire ou que l’utilisateur en demande un nouveau.</span><span class="sxs-lookup"><span data-stu-id="45d4e-136">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="45d4e-137">Toutefois, les informations de compte d’utilisateur suivantes ne sont pas déplacées vers le nouveau serveur :</span><span class="sxs-lookup"><span data-stu-id="45d4e-137">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="45d4e-138">Contenu de la réunion, par exemple les présentations PowerPoint, le contenu du tableau blanc et les données de sondage</span><span class="sxs-lookup"><span data-stu-id="45d4e-138">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="45d4e-139">Pour déplacer le contenu qui a été partagé lors de réunions, utilisez le paramètre MoveMeetingContent de la cmdlet Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="45d4e-139">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="45d4e-140">Pour plus d’informations sur l’utilisation de cette cmdlet, voir [Move-Csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) dans la documentation sur les applets de commande Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="45d4e-140">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="45d4e-141">Migration de réunions à partir d’Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="45d4e-141">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="45d4e-142">Les réunions Office Communications Server 2007 R2 sont soit des téléconférences (préfixe d’URL conf://), soit des conférences Web (préfixe d’URL meet://).</span><span class="sxs-lookup"><span data-stu-id="45d4e-142">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="45d4e-143">Lync Server 2013 ne prend pas en charge ces conférences conf://et meet://, et celles-ci ne sont pas migrées avec le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="45d4e-143">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="45d4e-144">Après la migration, vous devez demander aux utilisateurs de mettre à jour les liens des réunions en ligne qu’ils ont planifiées.</span><span class="sxs-lookup"><span data-stu-id="45d4e-144">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="45d4e-145">Ils peuvent effectuer cette opération après avoir installé le client Lync 2013 en ouvrant une invitation à une réunion planifiée, qui met à jour l’URL de la réunion et en renvoyant l’invitation aux participants.</span><span class="sxs-lookup"><span data-stu-id="45d4e-145">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="45d4e-146">Expérience utilisateur pendant la migration Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="45d4e-146">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="45d4e-147">Cette section fournit un résumé de l’expérience de conférence des utilisateurs lors de la migration à partir de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="45d4e-147">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="45d4e-148">Pour plus d’informations sur la façon dont les clients Lync Server 2013 peuvent coexister et interagir avec les versions précédentes du client et du serveur, consultez la rubrique [interopérabilité des clients dans Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="45d4e-148">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="45d4e-149">Rejoindre des réunions Lync Server 2010 avec un client Lync 2013</span><span class="sxs-lookup"><span data-stu-id="45d4e-149">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="45d4e-150">Lors de la migration à partir de Lync Server 2010, il peut y avoir une période de coexistence lorsque les utilisateurs rejoignent des réunions Lync Server 2010 avec un client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="45d4e-150">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="45d4e-151">Ces utilisateurs ont accès aux fonctionnalités clientes de Lync 2013 avec les exceptions suivantes :</span><span class="sxs-lookup"><span data-stu-id="45d4e-151">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="45d4e-152">Dans les options de gestion des **participants** , qui sont accessibles en pointant sur l’icône contacts dans la fenêtre de la réunion, l’option **aucun message instantané** ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="45d4e-152">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="45d4e-153">La vue de la galerie ne fonctionne pas dans les vidéoconférences.</span><span class="sxs-lookup"><span data-stu-id="45d4e-153">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="45d4e-154">L’utilisateur voit uniquement le haut-parleur actif au lieu de tous les haut-parleurs.</span><span class="sxs-lookup"><span data-stu-id="45d4e-154">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="45d4e-155">Dans la liste des options de **sélection de disposition** , le **mode Galerie** n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="45d4e-155">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="45d4e-156">La liste des participants s’affiche par défaut dans les vidéoconférences.</span><span class="sxs-lookup"><span data-stu-id="45d4e-156">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="45d4e-157">Lorsque vous cliquez avec le bouton droit de la souris sur un utilisateur dans la liste des participants, les options **verrouiller les vidéos en vedette** de la vidéo et **accrocher aux participants de la Galerie** ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="45d4e-157">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="45d4e-158">Expérience utilisateur pendant la migration d’Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="45d4e-158">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="45d4e-159">Cette section fournit un résumé de l’expérience de conférence des utilisateurs lors de la migration à partir d’Office Communications Server 2007 R2, avant et après l’installation de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="45d4e-159">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="45d4e-160">Pour plus d’informations sur la façon dont les clients Lync Server 2013 peuvent coexister et interagir avec les versions précédentes du client et du serveur, consultez la rubrique [interopérabilité des clients dans Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="45d4e-160">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="45d4e-161">Après la migration du compte d’utilisateur, avant l’installation de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="45d4e-161">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="45d4e-162">Après la migration d’un utilisateur vers le serveur Lync Server 2013, mais avant l’installation de nouveaux clients, les utilisateurs d’Office Communicator 2007 R2 peuvent continuer à utiliser leur client existant sur Lync Server 2013 pour les fonctionnalités de présence et de messagerie instantanée, mais pas les fonctionnalités de conférence. éditions.</span><span class="sxs-lookup"><span data-stu-id="45d4e-162">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="45d4e-163">Après la migration du compte d’utilisateur, après l’installation de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="45d4e-163">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="45d4e-164">Lorsqu’un utilisateur migré installe Lync 2013, le complément de réunion en ligne pour Lync 2013 est également installé.</span><span class="sxs-lookup"><span data-stu-id="45d4e-164">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="45d4e-165">Cela entraîne les effets suivants :</span><span class="sxs-lookup"><span data-stu-id="45d4e-165">This has the following effects:</span></span>

  - <span data-ttu-id="45d4e-166">Toutes les réunions planifiées ensuite utilisent le nouveau format de réunion, avec une adresse https:// au lieu d’une adresse Live Meeting meet:// héritée.</span><span class="sxs-lookup"><span data-stu-id="45d4e-166">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="45d4e-167">Dans un déploiement informatique géré de Lync 2013, l’administrateur a la possibilité de désinstaller le complément de conférence pour Microsoft Office Outlook, qui est utilisé pour planifier des réunions basées sur le serveur et le service Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="45d4e-167">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="45d4e-168">Cependant, certains utilisateurs doivent peut-être continuer à planifier les réunions du service Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="45d4e-168">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="45d4e-169">Dans ce cas, vous pouvez autoriser les deux compléments à coexister.</span><span class="sxs-lookup"><span data-stu-id="45d4e-169">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="45d4e-170">Réunions avec des organisations fédérées qui utilisent des clients précédents</span><span class="sxs-lookup"><span data-stu-id="45d4e-170">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="45d4e-171">Les utilisateurs des organisations fédérées qui utilisent Microsoft Office Communicator 2007 ne peuvent pas rejoindre les réunions Lync Server 2013 au sein de votre organisation si ces réunions sont verrouillées par l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="45d4e-171">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="45d4e-172">Vous devez replanifier ces réunions dans Lync Server 2013 afin que les participants fédérés rejoignent la réunion à l’aide de la nouvelle URL de réunion https://, ils peuvent utiliser Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="45d4e-172">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

