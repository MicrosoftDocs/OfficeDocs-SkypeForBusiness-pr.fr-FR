---
title: Création des stratégies de conférence dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Résumé : Apprenez à créer des stratégies de conférence dans Skype pour Business Server 2015.'
ms.openlocfilehash: 301474d57998d5c9a794a978c4ec8877b1e53bc7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="955fc-103">Création des stratégies de conférence dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="955fc-103">Create conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="955fc-104">**Résumé :** Apprenez à créer des stratégies de conférence dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="955fc-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="955fc-105">Vous pouvez créer des stratégies de conférence à l’aide de Skype pour le panneau de configuration de Business Server ou à l’aide de Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="955fc-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="955fc-106">Créer des stratégies de conférence pour le panneau de configuration de Business Server à l’aide de Skype</span><span class="sxs-lookup"><span data-stu-id="955fc-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="955fc-107">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="955fc-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="955fc-108">Ouvrez Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="955fc-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="955fc-109">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.</span><span class="sxs-lookup"><span data-stu-id="955fc-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="955fc-110">Cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="955fc-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="955fc-p101">Pour créer une stratégie au niveau de l’utilisateur, cliquez sur **Stratégie utilisateur**. Dans **Nouvelle stratégie de conférence**, dans **Nom**, tapez un nom descriptif pour la stratégie.</span><span class="sxs-lookup"><span data-stu-id="955fc-p101">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="955fc-p102">Pour créer une stratégie au niveau site, cliquez sur **Stratégie de site**. Dans la zone de recherche **Sélectionner un site**, tapez entièrement ou partiellement le nom du site pour lequel vous voulez créer une stratégie. Dans la liste des sites, cliquez sur le site voulu, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="955fc-p102">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="955fc-116">Le nom du site devient le nom de la stratégie de conférence. Il ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="955fc-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="955fc-117">Dans **Description**, tapez la description de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="955fc-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="955fc-p103">Sous **Stratégie de l’organisateur**, dans **Taille maximale de la réunion**, tapez le nombre maximal d’utilisateurs autorisés à participer à une réunion. Par défaut, la taille maximale de la réunion est définie sur 250.</span><span class="sxs-lookup"><span data-stu-id="955fc-p103">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="955fc-120">Pour empêcher les utilisateurs d’inviter des utilisateurs anonymes aux réunions, désactivez la case à cocher **Autoriser les participants à inviter des utilisateurs anonymes**.</span><span class="sxs-lookup"><span data-stu-id="955fc-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="955fc-121">Les utilisateurs anonymes sont des utilisateurs qui n’ont pas d’informations d’identification des Services de votre organisation de domaine Active Directory et qui, par conséquent, ne sont pas authentifiés.</span><span class="sxs-lookup"><span data-stu-id="955fc-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="955fc-122">Par défaut, les utilisateurs peuvent inviter des utilisateurs anonymes aux réunions.</span><span class="sxs-lookup"><span data-stu-id="955fc-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="955fc-123">Dans **Enregistrement**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="955fc-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="955fc-p105">Pour interdire aux participants d’enregistrer les réunions, cliquez sur **Aucun**. Il s’agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="955fc-p105">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
   - <span data-ttu-id="955fc-126">Pour autoriser les participants à enregistrer les réunions, cliquez sur **Activer l’enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="955fc-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="955fc-p106">Pour autoriser les participants externes à enregistrer les réunions, activez la case à cocher **Autoriser les participants fédérés et anonymes à enregistrer**. Par défaut, le système interdit aux participants externes d’enregistrer les réunions.</span><span class="sxs-lookup"><span data-stu-id="955fc-p106">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="955fc-129">Dans **Audio/vidéo**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="955fc-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="955fc-130">Pour interdire l’utilisation de l’audio et de la vidéo, cliquez sur **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="955fc-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="955fc-131">Pour autoriser l’utilisation de l’audio mais pas de la vidéo, cliquez sur **Activer Audio sur IP**.</span><span class="sxs-lookup"><span data-stu-id="955fc-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="955fc-p107">Pour autoriser l’utilisation de l’audio et de la vidéo, cliquez sur **Activer l’audio/la vidéo IP**. Il s’agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="955fc-p107">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>
    
11. <span data-ttu-id="955fc-134">Si vous avez choisi d’autoriser l’utilisation de l’audio dans **Audio/vidéo**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="955fc-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="955fc-p108">Pour empêcher les utilisateurs de rejoindre la réunion via un appel à distance, désactivez la case à cocher **Activer la conférence rendez-vous RTC**. Par défaut, les utilisateurs peuvent accéder aux réunions par le biais du réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="955fc-p108">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="955fc-p109">Si vous autorisez les utilisateurs à accéder aux réunions à distance et que vous souhaitez autoriser les utilisateurs non authentifiés (anonymes) à rejoindre une réunion via un appel téléphonique sortant, activez la case à cocher **Autoriser l’accès sortant des participants anonymes**. Avec l’appel téléphonique sortant, le serveur de conférence appelle l’utilisateur et celui-ci répond au téléphone pour rejoindre la réunion. Par défaut, les utilisateurs anonymes ne peuvent pas rejoindre une réunion via un appel téléphonique sortant.</span><span class="sxs-lookup"><span data-stu-id="955fc-p109">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="955fc-140">Si vous décidez d’autoriser l’utilisation de la vidéo dans **Audio/vidéo**, activez la case à cocher **Autoriser plusieurs flux vidéo**.</span><span class="sxs-lookup"><span data-stu-id="955fc-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="955fc-141">Dans **Collaboration de données**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="955fc-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="955fc-142">Pour empêcher la collaboration de données, cliquez sur **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="955fc-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="955fc-p110">Pour autoriser la collaboration de données, cliquez sur **Activer la collaboration de données**. Il s’agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="955fc-p110">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>
    
14. <span data-ttu-id="955fc-145">Si vous avez choisi d’autoriser la collaboration de données dans **Collaboration de données**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="955fc-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="955fc-p111">Pour interdire les téléchargements externes, désactivez la case à cocher **Autoriser les participants fédérés et anonymes à télécharger du contenu**. Par défaut, les utilisateurs externes peuvent télécharger du contenu.</span><span class="sxs-lookup"><span data-stu-id="955fc-p111">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
    - <span data-ttu-id="955fc-p112">Pour interdire les transferts de fichiers, désactivez la case à cocher **Autoriser les participants à transférer des fichiers**. Par défaut, les utilisateurs peuvent transférer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="955fc-p112">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="955fc-p113">Pour interdire l’utilisation des annotations, désactivez la case à cocher **Activer les annotations**. Pour autoriser l’utilisation des annotations dans les présentations PowerPoint partagées, désactivez la case à cocher **Activer les annotations PowerPoint**. Par défaut, les annotations sont autorisées.</span><span class="sxs-lookup"><span data-stu-id="955fc-p113">To prevent the use of annotations, clear the **Enable annotations** check box. To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**. By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="955fc-p114">Pour interdire l’utilisation des sondages, désactivez la case à cocher **Activer les sondages**. Par défaut, les sondages sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="955fc-p114">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="955fc-155">Dans **Partage d’application**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="955fc-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="955fc-156">Pour interdire l’utilisation du partage d’application, cliquez sur **Désactiver le partage d’application**.</span><span class="sxs-lookup"><span data-stu-id="955fc-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="955fc-p115">Pour autoriser l’utilisation du partage d’application, cliquez sur **Activer le partage d’application**. Il s’agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="955fc-p115">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>
    
16. <span data-ttu-id="955fc-159">Si vous avez choisi d’autoriser le partage d’application dans **Partage d’application**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="955fc-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="955fc-p116">Pour empêcher les participants à la réunion de prendre le contrôle du partage d’application, désactivez la case à cocher **Autoriser les participants à prendre le contrôle**. Par défaut, les participants peuvent prendre le contrôle du partage d’application.</span><span class="sxs-lookup"><span data-stu-id="955fc-p116">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="955fc-p117">Si vous avez choisi d’autoriser les participants à la réunion à prendre le contrôle du partage d’application, activez la case à cocher **Autoriser les participants fédérés et anonymes à prendre le contrôle** pour autoriser les utilisateurs externes à prendre le contrôle du partage d’application. Par défaut, les utilisateurs externes ne peuvent pas prendre le contrôle du partage d’application.</span><span class="sxs-lookup"><span data-stu-id="955fc-p117">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="955fc-164">Sous **Stratégie de participant**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="955fc-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="955fc-165">Pour interdire le partage d’application et le partage du Bureau, cliquez sur **Désactiver le partage d’application et de Bureau**.</span><span class="sxs-lookup"><span data-stu-id="955fc-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="955fc-166">Pour autoriser le partage d’application mais pas le partage du Bureau, cliquez sur **Activer le partage d’application**.</span><span class="sxs-lookup"><span data-stu-id="955fc-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="955fc-p118">Pour autoriser le partage d’application et le partage du Bureau, cliquez sur **Activer le partage d’application et de Bureau**. Il s’agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="955fc-p118">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>
    
18. <span data-ttu-id="955fc-p119">Pour interdire les transferts de fichiers d’homologue à homologue, désactivez la case à cocher **Autoriser le transfert de fichiers entre homologues**. Par défaut, les transferts de fichiers d’homologue à homologue sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="955fc-p119">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="955fc-p120">Pour autoriser l’enregistrement d’homologue à homologue, activez la case à cocher **Activer l’enregistrement entre homologues**. Par défaut, l’enregistrement d’homologue à homologue n’est pas autorisé.</span><span class="sxs-lookup"><span data-stu-id="955fc-p120">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="955fc-p121">Pour autoriser les participants à participer avec plusieurs flux vidéo, activez la case à cocher **Autoriser les participants à participer avec plusieurs flux vidéo**. Par défaut, les flux vidéo multiples sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="955fc-p121">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="955fc-175">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="955fc-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="955fc-176">Créer des stratégies de la conférence à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="955fc-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="955fc-177">Pour créer des stratégies de conférence, utilisez l’applet de commande **New-Cs ConferencingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="955fc-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="955fc-178">L’exemple suivant crée une nouvelle stratégie de conférence avec l’identité SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="955fc-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="955fc-179">Cette stratégie utilise toutes les valeurs par défaut d’une stratégie de conférence, à l’exception de la valeur suivante : MaxMeetingSize.</span><span class="sxs-lookup"><span data-stu-id="955fc-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="955fc-180">Dans cet exemple, la taille maximale d’une réunion sera définie sur 50 plutôt que sur 250, soit la valeur par défaut :</span><span class="sxs-lookup"><span data-stu-id="955fc-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="955fc-181">Pour plus d’informations, y compris une description de la syntaxe complète et d’une liste de paramètres, consultez [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="955fc-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

