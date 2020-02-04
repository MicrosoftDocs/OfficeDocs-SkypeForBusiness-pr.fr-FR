---
title: 'Lync Server 2013 : considérations de migration pour les réunions'
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
ms.openlocfilehash: 6af94514360509d4f608a21228b2fecf9a522007
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="6a5c0-102">Remarques concernant la migration des réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a5c0-102">Migration considerations for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a5c0-103">_**Dernière modification de la rubrique :** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="6a5c0-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="6a5c0-104">Les rubriques suivantes sont abordées dans cette section :</span><span class="sxs-lookup"><span data-stu-id="6a5c0-104">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="6a5c0-105">Modifications apportées aux réunions dans Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a5c0-105">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="6a5c0-106">Migration des utilisateurs en fonction des besoins de leurs conférences</span><span class="sxs-lookup"><span data-stu-id="6a5c0-106">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="6a5c0-107">Migration des réunions existantes et du contenu de la réunion</span><span class="sxs-lookup"><span data-stu-id="6a5c0-107">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="6a5c0-108">Utilisation de l’interface utilisateur lors de la migration Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6a5c0-108">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="6a5c0-109">Utilisation de l’interface utilisateur lors de la migration Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6a5c0-109">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="6a5c0-110">Compatibilité entre Microsoft Lync 2013 et les réunions sur les versions antérieures du serveur</span><span class="sxs-lookup"><span data-stu-id="6a5c0-110">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="6a5c0-111">Modifications apportées aux réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a5c0-111">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="6a5c0-112">**Fonctionnalités de Lync Server 2013.**    Lync Server 2013 fournit de nouvelles fonctionnalités de conférence qui deviennent accessibles aux utilisateurs une fois leur compte déplacé vers Lync Server 2013 et se connectant avec le client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-112">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="6a5c0-113">Les nouvelles fonctionnalités sont présentées dans les [nouvelles fonctionnalités de conférence de Lync server 2013](lync-server-2013-new-conferencing-features.md) et [les nouveautés pour les clients de Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="6a5c0-113">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="6a5c0-114">**URL de la réunion.**    Comme dans lync Server 2010, toutes les réunions nouvellement planifiées dans lync Server 2013 ont un préfixe d’URL de https://et les réunions existantes sont migrées avec les comptes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-114">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="6a5c0-115">Toutefois, Lync Server 2013 ne prend pas en charge la conférence téléphonique Office Communications Server 2007 R2 (préfixe d’URL conf://) ou la conférence Web (préfixe d’URL meet://).</span><span class="sxs-lookup"><span data-stu-id="6a5c0-115">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="6a5c0-116">Pour plus d’informations, voir « migration des réunions à partir d’Office Communications Server 2007 R2 » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-116">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="6a5c0-117">**Prise en charge du client.**    À la différence de lync Server 2010, lync Server 2013 ne prend pas en charge les clients Office Communicator pour les conférences.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-117">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="6a5c0-118">Vous ne pouvez pas utiliser les clients suivants pour participer aux réunions planifiées par le biais du complément réunion en ligne pour Lync 2013 :</span><span class="sxs-lookup"><span data-stu-id="6a5c0-118">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="6a5c0-119">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6a5c0-119">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="6a5c0-120">Microsoft Office Communications Server 2007 R2 attendant</span><span class="sxs-lookup"><span data-stu-id="6a5c0-120">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="6a5c0-121">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="6a5c0-121">Office Communicator 2007</span></span>

  - <span data-ttu-id="6a5c0-122">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="6a5c0-122">Office Live Meeting 2007</span></span>

<span data-ttu-id="6a5c0-123">Lors de la migration, les utilisateurs d’Office Communicator 2007 R2 doivent utiliser Lync Web App 2013 pour participer aux réunions Lync Server 2013 tant que leurs clients n’ont pas été mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-123">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="6a5c0-124">Notez que les utilisateurs d’Office Communicator 2007 R2 peuvent continuer à utiliser leur client existant sur Lync Server 2013 pour les fonctionnalités de présence et de messagerie instantanée, mais pas les fonctionnalités de conférence non prises en charge.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-124">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="6a5c0-125">Migration des utilisateurs en fonction des besoins de leurs conférences</span><span class="sxs-lookup"><span data-stu-id="6a5c0-125">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="6a5c0-126">**Organisateurs de réunion fréquents.**    Envisagez de migrer les organisateurs de la réunion fréquents au début de la procédure de manière à ce qu’ils tirent parti des nouvelles fonctionnalités de lync Server 2013 et Lync 2013 présentées dans les [nouvelles fonctionnalités de conférence de Lync Server 2013](lync-server-2013-new-conferencing-features.md) et [des nouveautés pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="6a5c0-126">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="6a5c0-127">**Utilisateurs Live Meeting.**    Si vous effectuez une migration à partir d’Office Communications Server 2007 R2 et que vous avez des utilisateurs qui ont besoin de fonctionnalités de conférences Web spécifiques à Live Meeting, en particulier la prise en charge de réunions de grande envergure et de salles de séparation, vous disposez des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="6a5c0-127">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="6a5c0-128">Conseillez aux organisateurs d’utiliser le service Live Meeting, s’il est disponible dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-128">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="6a5c0-129">Laissez les organisateurs hébergés sur la version antérieure d’Office Communications Server pour qu’ils puissent continuer à planifier des conférences Web Live Meeting basées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-129">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="6a5c0-130">Migration des réunions existantes et du contenu de la réunion</span><span class="sxs-lookup"><span data-stu-id="6a5c0-130">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="6a5c0-131">Migration de réunions à partir de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6a5c0-131">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="6a5c0-132">Lorsque vous déplacez un utilisateur de Lync Server 2010 vers Lync Server 2013, les informations suivantes sont déplacées avec le compte de l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="6a5c0-132">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="6a5c0-133">Réunions déjà planifiées par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-133">Meetings already scheduled by the user.</span></span> <span data-ttu-id="6a5c0-134">Cela inclut les répertoires de conférences et les données de conférence.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-134">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="6a5c0-135">Code confidentiel (PIN) de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-135">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="6a5c0-136">Le code confidentiel actuel de l’utilisateur continue de fonctionner tant qu’il n’a pas expiré ou que l’utilisateur ne demande pas de nouveau code secret.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-136">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="6a5c0-137">Toutefois, les informations de compte d’utilisateur suivantes ne sont pas déplacées vers le nouveau serveur :</span><span class="sxs-lookup"><span data-stu-id="6a5c0-137">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="6a5c0-138">Contenu de la réunion, par exemple présentations PowerPoint, contenu de tableau blanc et données de sondage</span><span class="sxs-lookup"><span data-stu-id="6a5c0-138">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="6a5c0-139">Pour déplacer le contenu partagé dans les réunions, utilisez le paramètre MoveMeetingContent de l’applet de passe Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-139">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="6a5c0-140">Pour plus d’informations sur l’utilisation de cette applet de connexion, voir [Move-Csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) dans la documentation sur les applets de applet de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-140">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="6a5c0-141">Migration des réunions à partir d’Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6a5c0-141">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="6a5c0-142">Les réunions Office Communications Server 2007 R2 sont des conférences téléphoniques (préfixe d’URL conf://) ou des conférences Web (préfixe d’URL meet://).</span><span class="sxs-lookup"><span data-stu-id="6a5c0-142">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="6a5c0-143">Lync Server 2013 ne prend pas en charge ces conférences conf://et meet://antérieures, et elles ne sont pas migrées en même temps que le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-143">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="6a5c0-144">Après la migration, vous devez demander aux utilisateurs de mettre à jour les liens pour toutes les réunions en ligne qu’ils ont planifiées.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-144">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="6a5c0-145">Pour ce faire, elle peut procéder après l’installation du client 2013 Lync en ouvrant une invitation à une réunion planifiée, qui met à jour l’URL de la réunion et renvoyant l’invitation aux participants.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-145">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="6a5c0-146">Utilisation de l’interface utilisateur lors de la migration Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6a5c0-146">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="6a5c0-147">Cette section fournit un récapitulatif de la qualité de conférences des utilisateurs lors de la migration à partir de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-147">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="6a5c0-148">Pour plus d’informations sur la façon dont les clients Lync Server 2013 peuvent coexister avec les versions antérieures du serveur et le client, voir [interopérabilité client dans Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="6a5c0-148">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="6a5c0-149">Rejoindre des réunions Lync Server 2010 avec un client 2013 Lync</span><span class="sxs-lookup"><span data-stu-id="6a5c0-149">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="6a5c0-150">Lors de la migration à partir de Lync Server 2010, il est possible que les utilisateurs rejoignent des réunions Lync Server 2010 avec un client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-150">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="6a5c0-151">Ces utilisateurs ont accès aux fonctionnalités du client 2013 Lync et présentent les exceptions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6a5c0-151">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="6a5c0-152">Dans les options de gestion des **participants** accessibles en pointant sur l’icône personnes dans la fenêtre de la réunion, l’option **aucun message instantané** ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-152">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="6a5c0-153">Le mode Galerie ne fonctionne pas dans les conférences vidéo.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-153">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="6a5c0-154">L’utilisateur ne voit que le haut-parleur actif au lieu de ses haut-parleurs.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-154">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="6a5c0-155">Dans la liste des options **choisir une disposition, la** **vue Galerie** n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="6a5c0-155">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="6a5c0-156">La liste des participants s’affiche par défaut dans les conférences vidéo.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-156">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="6a5c0-157">Lorsque vous cliquez avec le bouton droit sur un utilisateur dans la liste des participants, les options **verrouiller les actualités vidéo** et **épingler aux participants à la Galerie** ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-157">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="6a5c0-158">Utilisation de l’interface utilisateur lors de la migration Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6a5c0-158">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="6a5c0-159">Cette section fournit un résumé de l’interface des utilisateurs lors de la migration à partir d’Office Communications Server 2007 R2, avant et après l’installation de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-159">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="6a5c0-160">Pour plus d’informations sur la façon dont les clients Lync Server 2013 peuvent coexister avec les versions antérieures du serveur et le client, voir [interopérabilité client dans Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="6a5c0-160">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="6a5c0-161">Après la migration du compte d’utilisateur, avant l’installation de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6a5c0-161">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="6a5c0-162">Après la migration d’un utilisateur vers le serveur Lync Server 2013, mais avant l’installation de nouveaux clients, les utilisateurs d’Office Communicator 2007 R2 peuvent continuer à utiliser leur client existant sur Lync Server 2013 pour les fonctionnalités de présence et de messagerie instantanée, mais pas les fonctionnalités de conférence. pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-162">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="6a5c0-163">Après la migration du compte d’utilisateur après l’installation de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6a5c0-163">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="6a5c0-164">Lorsqu’un utilisateur migré installe Lync 2013, le complément réunion en ligne pour Lync 2013 est également installé.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-164">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="6a5c0-165">Cela a les effets suivants :</span><span class="sxs-lookup"><span data-stu-id="6a5c0-165">This has the following effects:</span></span>

  - <span data-ttu-id="6a5c0-166">Toutes les réunions planifiées par la suite utilisent le nouveau format de réunion, qui utilise une adresse de https://à la place de l’adresse de réunion meet://Live Meeting héritée.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-166">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="6a5c0-167">Dans le cas d’un déploiement géré par le service informatique de Lync 2013, l’administrateur a la possibilité de désinstaller le complément de conférence pour Microsoft Office Outlook, qui est utilisé pour planifier des réunions serveur et de réunion en temps réel.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-167">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="6a5c0-168">Néanmoins, il est possible que vous ayez des utilisateurs qui ont besoin de continuer à planifier des réunions du service Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-168">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="6a5c0-169">Dans ce cas, vous pouvez autoriser les deux compléments à cohabiter.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-169">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="6a5c0-170">Réunions avec des organisations fédérées utilisant des clients antérieurs</span><span class="sxs-lookup"><span data-stu-id="6a5c0-170">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="6a5c0-171">Les utilisateurs d’organisations fédérées qui utilisent Microsoft Office Communicator 2007 ne peuvent pas rejoindre les réunions Lync Server 2013 au sein de votre organisation si celles-ci sont verrouillées par l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-171">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="6a5c0-172">Vous devez reprogrammer ces réunions dans Lync Server 2013 de sorte que les participants fédérés rejoignent la réunion à l’aide de la nouvelle URL de la réunion https://, ils peuvent utiliser Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="6a5c0-172">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

