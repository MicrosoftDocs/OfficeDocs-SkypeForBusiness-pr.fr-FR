---
title: Configuration de Lync Server 2013 pour utiliser l’archivage Microsoft Exchange Server 2013
description: Configuration de Lync Server 2013 pour utiliser l’archivage Microsoft Exchange Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80b0673071ec38246e366fe7556b39bd495895d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542940"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a><span data-ttu-id="1a987-103">Configuration de Microsoft Lync Server 2013 pour utiliser l’archivage Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a987-103">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a987-104">_**Dernière modification de la rubrique :** 2014-06-24_</span><span class="sxs-lookup"><span data-stu-id="1a987-104">_**Topic Last Modified:** 2014-06-24_</span></span>

<span data-ttu-id="1a987-105">Microsoft Lync Server 2013 offre aux administrateurs la possibilité d’archiver les transcriptions de messagerie instantanée et de conférence Web dans la boîte aux lettres de Microsoft Exchange Server 2013 d’un utilisateur plutôt que dans une base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1a987-105">Microsoft Lync Server 2013 gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Microsoft Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="1a987-106">Si vous activez cette option, les transcriptions sont écrites dans le dossier Purges de la boîte aux lettres de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a987-106">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="1a987-107">Il s’agit d’un dossier masqué qui se trouve dans le dossier Purges.</span><span class="sxs-lookup"><span data-stu-id="1a987-107">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="1a987-108">Bien que ce dossier ne soit pas visible par les utilisateurs finaux, le dossier est indexé par le moteur de recherche Exchange et peut être découvert à l’aide de la recherche de boîte aux lettres Exchange et/ou de Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a987-108">Although this folder is not visible to end-users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="1a987-109">Étant donné que les informations sont stockées dans le même dossier que celui utilisé par la fonctionnalité de blocage des In-Place Exchange (responsable de l’archivage des courriers électroniques et des autres communications Exchange), les administrateurs peuvent utiliser un seul outil pour rechercher toutes les communications électroniques archivées pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a987-109">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1a987-110">Pour désactiver complètement l’archivage de conversation Lync, vous devez également désactiver l’historique des conversations Lync.</span><span class="sxs-lookup"><span data-stu-id="1a987-110">To completely disable archiving of Lync conversation, you must also disable Lync conversation history.</span></span> <span data-ttu-id="1a987-111">Pour plus d’informations, consultez les rubriques suivantes : <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of Internal and External Communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>et <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="1a987-111">For more information, see the following topics: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>, and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span></span>



</div>

<span data-ttu-id="1a987-112">Pour archiver les transcriptions dans Exchange 2013, vous devez commencer par configurer l’authentification de serveur à serveur entre les deux serveurs.</span><span class="sxs-lookup"><span data-stu-id="1a987-112">In order to archive transcripts to Exchange 2013 you must begin by configuring server-to-server authentication between the two servers.</span></span> <span data-ttu-id="1a987-113">Une fois l’authentification de serveur à serveur mise en place, vous pouvez effectuer les tâches suivantes dans Microsoft Lync Server 2013 (Notez que, en fonction de votre configuration et de votre configuration, il se peut que vous n’ayez pas besoin d’effectuer toutes ces tâches) :</span><span class="sxs-lookup"><span data-stu-id="1a987-113">After server-to-server authentication is in place you can then carry out the following tasks in Microsoft Lync Server 2013 (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1.  <span data-ttu-id="1a987-114">Activez l’archivage Exchange en modifiant vos paramètres de configuration de l’archivage Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a987-114">Enable Exchange archiving by modifying your Lync Server archiving configuration settings.</span></span> <span data-ttu-id="1a987-115">Cette étape est nécessaire pour tous les déploiements.</span><span class="sxs-lookup"><span data-stu-id="1a987-115">This step is required for all deployments.</span></span>

2.  <span data-ttu-id="1a987-116">Activer l’archivage des communications internes et/ou externes pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1a987-116">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="1a987-117">Cette étape est nécessaire pour tous les déploiements.</span><span class="sxs-lookup"><span data-stu-id="1a987-117">This step is required for all deployments.</span></span>

3.  <span data-ttu-id="1a987-118">Configurer la propriété ExchangeArchivingPolicy pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a987-118">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="1a987-119">Cette étape n’est requise que dans Lync Server et Exchange se situent dans des forêts différentes.</span><span class="sxs-lookup"><span data-stu-id="1a987-119">This step is only required in Lync Server and Exchange are located in different forests.</span></span>

<div>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="1a987-120">Étape 1 : activation de l’archivage Exchange</span><span class="sxs-lookup"><span data-stu-id="1a987-120">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="1a987-121">L’archivage dans Lync Server est principalement géré à l’aide des paramètres de configuration de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="1a987-121">Archiving in Lync Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="1a987-122">Lors de l’installation de Lync Server 2013, une seule collection globale de ces paramètres vous est automatiquement attribuée.</span><span class="sxs-lookup"><span data-stu-id="1a987-122">When you install Lync Server 2013 you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="1a987-123">(Les administrateurs peuvent éventuellement créer de nouvelles collections de paramètres d’archivage au niveau de l’étendue site.) Par défaut, l’archivage n’est pas activé dans les paramètres globaux et l’archivage Exchange est activé dans ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="1a987-123">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="1a987-124">Pour pouvoir utiliser l’archivage Exchange, les administrateurs doivent configurer les propriétés EnableArchiving et EnableExchangeArchiving dans ces paramètres de configuration.</span><span class="sxs-lookup"><span data-stu-id="1a987-124">In order to use Exchange archiving administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="1a987-125">La propriété EnableArchiving peut avoir l’une des trois valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="1a987-125">The EnableArchiving property can be set to one of three possible values:</span></span>

  - <span data-ttu-id="1a987-126">**Aucun**.</span><span class="sxs-lookup"><span data-stu-id="1a987-126">**None**.</span></span> <span data-ttu-id="1a987-127">L’archivage est désactivé.</span><span class="sxs-lookup"><span data-stu-id="1a987-127">Archiving is disabled.</span></span> <span data-ttu-id="1a987-128">Il s’agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="1a987-128">This is the default value.</span></span> <span data-ttu-id="1a987-129">Si EnableArchiving est défini sur None, rien ne sera archivé dans votre base de données d’archivage Lync Server ou dans Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="1a987-129">If EnableArchiving is set to None then nothing will be archived in either your Lync Server archiving database or in Exchange 2013.</span></span>

  - <span data-ttu-id="1a987-130">**ImOnly**Impropres.</span><span class="sxs-lookup"><span data-stu-id="1a987-130">**ImOnly**.</span></span> <span data-ttu-id="1a987-131">Seules les transcriptions de message instantané sont archivées.</span><span class="sxs-lookup"><span data-stu-id="1a987-131">Only instant message transcripts are archived.</span></span> <span data-ttu-id="1a987-132">Si l’archivage Exchange est activé, ces transcriptions seront archivées dans Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="1a987-132">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="1a987-133">Si l’archivage Exchange est désactivé, ces transcriptions seront archivées dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a987-133">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

  - <span data-ttu-id="1a987-134">**ImAndWebConf**.</span><span class="sxs-lookup"><span data-stu-id="1a987-134">**ImAndWebConf**.</span></span> <span data-ttu-id="1a987-135">À la fois les transcriptions de message instantanée et celles de conférence web sont archivées.</span><span class="sxs-lookup"><span data-stu-id="1a987-135">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="1a987-136">Si l’archivage Exchange est activé, ces transcriptions seront archivées dans Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="1a987-136">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="1a987-137">Si l’archivage Exchange est désactivé, ces transcriptions seront archivées dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a987-137">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

<span data-ttu-id="1a987-138">La propriété EnableExchangeArchiving est une valeur booléenne : définissez EnableExchangeArchiving sur true ($True) pour activer l’archivage Exchange ou définissez EnableExchangeArchiving sur false ($False) pour désactiver l’archivage Exchange.</span><span class="sxs-lookup"><span data-stu-id="1a987-138">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="1a987-139">Par exemple, cette commande permet l’archivage des transcriptions de messagerie instantanée et active l’archivage Exchange :</span><span class="sxs-lookup"><span data-stu-id="1a987-139">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

<span data-ttu-id="1a987-140">Pour désactiver l’archivage Exchange, utilisez une commande semblable à la suivante, qui active l’archivage de la messagerie instantanée mais désactive l’archivage dans Exchange (en d’autres termes, les transcriptions seront archivées dans Lync Server) :</span><span class="sxs-lookup"><span data-stu-id="1a987-140">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Lync Server):</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> <span data-ttu-id="1a987-141">Si la propriété EnableArchiving est définie sur None, Lync Server n’archive pas du tout les transcriptions de messagerie instantanée et de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="1a987-141">If the EnableArchiving property is set to None then Lync Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="1a987-142">Dans ce cas, le serveur ignorera simplement la valeur configurée pour EnableExchangeArchiving.</span><span class="sxs-lookup"><span data-stu-id="1a987-142">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>



</div>

<span data-ttu-id="1a987-143">L’archivage Exchange peut également être activé (ou désactivé) à l’aide du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a987-143">Exchange archiving can also be enabled (or disabled) by using the Lync Server Control Panel.</span></span> <span data-ttu-id="1a987-144">Pour ce faire, procédez de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="1a987-144">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="1a987-145">Dans le Panneau de configuration, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="1a987-145">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2.  <span data-ttu-id="1a987-146">Sous l’onglet **Configuration de l’archivage**, double-cliquez sur la collection de paramètres d’archivage à modifier (par exemple, la collection **Global**).</span><span class="sxs-lookup"><span data-stu-id="1a987-146">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3.  <span data-ttu-id="1a987-147">Dans le volet **Paramètre d’archivage**, cliquez sur la liste déroulante **Paramètre d’archivage**, puis sélectionnez **Archiver les sessions de messagerie instantanée** (pour archiver uniquement les sessions de messagerie instantanée) ou **Archiver les sessions de messagerie instantanée et de conférence web** (pour archiver les sessions de messagerie instantanée et les sessions de conférence web).</span><span class="sxs-lookup"><span data-stu-id="1a987-147">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4.  <span data-ttu-id="1a987-148">Après avoir choisi les éléments à archiver, activez la case à cocher **intégration Exchange Server** pour activer l’archivage Exchange.</span><span class="sxs-lookup"><span data-stu-id="1a987-148">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="1a987-149">Pour désactiver l’archivage Exchange, désactivez cette case à cocher.</span><span class="sxs-lookup"><span data-stu-id="1a987-149">To disable Exchange archiving, clear this checkbox.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a987-150">La case à cocher <STRONG>Intégration Exchange Server</STRONG> n’est pas disponible si <STRONG>Paramètre d’archivage</STRONG> est défini sur <STRONG>Désactiver l’archivage</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1a987-150">The <STRONG>Exchange Server integration</STRONG> checkbox will not be available if the <STRONG>Archiving setting</STRONG> is set to <STRONG>Disable archiving</STRONG>.</span></span> <span data-ttu-id="1a987-151">Vous devez d’abord activer l’archivage, puis activer l’archivage Exchange.</span><span class="sxs-lookup"><span data-stu-id="1a987-151">You must enable archiving first and then enable Exchange archiving.</span></span>



</div>

<span data-ttu-id="1a987-152">Si Lync Server 2013 et Exchange 2013 se trouvent dans la même forêt, l’archivage pour des utilisateurs individuels (ou au moins pour les utilisateurs qui disposent de comptes de messagerie sur Exchange 2013) est géré à l’aide des stratégies de blocage d’Exchange In-Place.</span><span class="sxs-lookup"><span data-stu-id="1a987-152">If Lync Server 2013 and Exchange 2013 are located in the same forest then archiving for individual users (or at least for users who have email accounts on Exchange 2013) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="1a987-153">Si certains de vos utilisateurs sont hébergés sur une version antérieure d’Exchange, l’archivage de ces utilisateurs sera géré à l’aide de stratégies d’archivage Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a987-153">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Lync Server archiving policies.</span></span> <span data-ttu-id="1a987-154">Notez que seuls les utilisateurs disposant de comptes sur Exchange 2013 peuvent faire en sorte que leurs transcriptions Lync soient archivées dans Exchange.</span><span class="sxs-lookup"><span data-stu-id="1a987-154">Note that only users with accounts on Exchange 2013 can have their Lync transcripts archived to Exchange.</span></span>

<span data-ttu-id="1a987-155">Si Lync Server 2013 et Exchange 2013 sont situés dans des forêts différentes, l’archivage pour des utilisateurs individuels est géré en configurant la propriété ExchangeArchivingPolicy pour chaque compte d’utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="1a987-155">If Lync Server 2013 and Exchange 2013 are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="1a987-156">Pour plus d’informations, voir l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="1a987-156">See Step 3 for more information.</span></span>

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="1a987-157">Étape 2 : Activation de l’archivage des communications internes et/ou externes</span><span class="sxs-lookup"><span data-stu-id="1a987-157">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="1a987-158">Une fois que vous avez activé l’archivage (et l’archivage Exchange), vous devez modifier les stratégies d’archivage appropriées afin de vous assurer que les sessions utilisateur sont effectivement archivées.</span><span class="sxs-lookup"><span data-stu-id="1a987-158">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="1a987-159">Notez que l’activation de l’archivage (étape 1) ne permet pas à Lync Server de commencer l’archivage des transcriptions de messagerie instantanée et de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="1a987-159">Note that simply enabling archiving (Step 1) does not cause Lync Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="1a987-160">Vous devez utiliser les stratégies d’archivage pour activer l’archivage interne et/ou externe.</span><span class="sxs-lookup"><span data-stu-id="1a987-160">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="1a987-161">Lorsque vous installez Lync Server 2013, vous installez également une stratégie d’archivage globale unique qui contient deux propriétés :</span><span class="sxs-lookup"><span data-stu-id="1a987-161">When you install Lync Server 2013 you also install a single, global archiving policy that contains two properties:</span></span>

  - <span data-ttu-id="1a987-p119">**ArchiveInternal**. Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication interne (celles qui impliquent uniquement des utilisateurs disposant d’un compte Active Directory dans votre organisation) seront archivées.</span><span class="sxs-lookup"><span data-stu-id="1a987-p119">**ArchiveInternal**. When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

  - <span data-ttu-id="1a987-p120">**ArchiveExternal**. Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication externe (les sessions qui impliquent au moins un utilisateur ne disposant pas d’un compte Active Directory dans votre organisation) seront archivées.</span><span class="sxs-lookup"><span data-stu-id="1a987-p120">**ArchiveExternal**. When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="1a987-166">Par défaut, ces deux propriétés ont la valeur Faux, ce qui signifie que ni les sessions de communication interne, ni les sessions de communication externe ne sont archivées.</span><span class="sxs-lookup"><span data-stu-id="1a987-166">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="1a987-167">Pour modifier la stratégie globale, vous pouvez utiliser Lync Server Management Shell et la cmdlet Set-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="1a987-167">To modify the global policy, you can use the Lync Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="1a987-168">Cette commande permet d’archiver à la fois les sessions de communication interne et externe :</span><span class="sxs-lookup"><span data-stu-id="1a987-168">This command enables the archiving of both internal and external communication sessions:</span></span>

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="1a987-p122">Vous pouvez également utiliser New-CsArchivingPolicy pour créer une stratégie au niveau du site ou par utilisateur. Par exemple, la commande suivante crée une stratégie d’archivage par utilisateur appelée RedmondArchivingPolicy :</span><span class="sxs-lookup"><span data-stu-id="1a987-p122">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope. For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="1a987-p123">Si vous créez une stratégie par utilisateur, vous devrez affecter cette stratégie aux utilisateurs appropriés. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1a987-p123">If you create a per-user policy you will then need to assign that policy to the appropriate users. For example:</span></span>

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

<span data-ttu-id="1a987-173">Les stratégies d’archivage peuvent également être gérées à l’aide du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a987-173">Archiving policies can also be managed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="1a987-174">Dans le Panneau de configuration, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="1a987-174">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="1a987-175">Pour modifier une stratégie existante, double-cliquez sur la stratégie (par exemple, Global) puis, dans le volet **Stratégie d’archivage**, activez ou désactivez les cases à cocher **Archiver les communications internes** et **Archiver les communications externes** en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="1a987-175">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="1a987-176">Pour créer une nouvelle stratégie d’archivage, cliquez sur **nouveau** , puis sélectionnez **stratégie de site** ou **stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="1a987-176">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="1a987-177">Si vous créez une nouvelle stratégie d’utilisateur, vous devez accéder aux comptes d’utilisateurs appropriés (sous l’onglet **Utilisateurs**), puis affecter à ces utilisateurs les nouvelles stratégies.</span><span class="sxs-lookup"><span data-stu-id="1a987-177">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="1a987-178">Étape 3 : Configuration de la propriété ExchangeArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="1a987-178">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="1a987-179">Si Lync Server 2013 et Exchange 2013 sont situés dans des forêts différentes, il ne suffit pas d’activer simplement l’archivage Exchange dans les paramètres de configuration de l’archivage. Cela n’entraîne pas l’archivage de la messagerie instantanée et des transcriptions de conférence Web dans Exchange.</span><span class="sxs-lookup"><span data-stu-id="1a987-179">If Lync Server 2013 and Exchange 2013 are located in different forests then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="1a987-180">Au lieu de cela, vous devez également configurer la propriété ExchangeArchivingPolicy sur chacun des comptes d’utilisateur Lync Server pertinents.</span><span class="sxs-lookup"><span data-stu-id="1a987-180">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Lync Server user accounts.</span></span> <span data-ttu-id="1a987-181">Cette propriété peut avoir l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="1a987-181">This property can be set to one of four possible values:</span></span>

1.  <span data-ttu-id="1a987-182">Non initialisée.</span><span class="sxs-lookup"><span data-stu-id="1a987-182">Uninitialized.</span></span> <span data-ttu-id="1a987-183">Indique que l’archivage sera basé sur les paramètres de conservation des In-Place configurés pour la boîte aux lettres Exchange de l’utilisateur ; si In-Place conservation n’a pas été activée sur la boîte aux lettres de l’utilisateur, les transcriptions de messagerie et de conférence Web de l’utilisateur sont archivées dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a987-183">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Lync Server.</span></span>

2.  <span data-ttu-id="1a987-184">**Valeur uselyncarchivingpolicy**.</span><span class="sxs-lookup"><span data-stu-id="1a987-184">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="1a987-185">Indique que les transcriptions de messagerie instantanée et de conférence Web de l’utilisateur doivent être archivées dans Lync Server et non dans Exchange.</span><span class="sxs-lookup"><span data-stu-id="1a987-185">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Lync Server rather than in Exchange.</span></span>

3.  <span data-ttu-id="1a987-186">**Noarchivage**.</span><span class="sxs-lookup"><span data-stu-id="1a987-186">**NoArchiving**.</span></span> <span data-ttu-id="1a987-187">Indique que les transcriptions de messagerie instantanée et de conférence web de l’utilisateur ne doivent pas être archivées.</span><span class="sxs-lookup"><span data-stu-id="1a987-187">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="1a987-188">Notez que ce paramètre remplace toutes les stratégies d’archivage Lync Server affectées à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a987-188">Note that this setting overrides any Lync Server archiving policies assigned to the user.</span></span>

4.  <span data-ttu-id="1a987-189">**ArchivingToExchange**.</span><span class="sxs-lookup"><span data-stu-id="1a987-189">**ArchivingToExchange**.</span></span> <span data-ttu-id="1a987-190">Indique que les transcriptions de messagerie instantanée et de conférence Web de l’utilisateur doivent être archivées dans Exchange, quel que soit le In-Place les paramètres qui ont été affectés à la boîte aux lettres de l’utilisateur (ou non).</span><span class="sxs-lookup"><span data-stu-id="1a987-190">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="1a987-191">Par exemple, pour configurer un compte d’utilisateur de manière à toujours archiver les transcriptions de messagerie instantanée et de conférence Web dans Exchange, vous pouvez utiliser une commande semblable à celle-ci à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="1a987-191">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="1a987-192">Si vous souhaitez définir la même stratégie d’archivage pour un groupe d’utilisateurs (par exemple, tous les utilisateurs hébergés sur un pool de serveurs d’inscriptions), vous pouvez utiliser une commande similaire à la suivante :</span><span class="sxs-lookup"><span data-stu-id="1a987-192">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="1a987-193">Notez que vous devez utiliser Lync Server Management Shell (et Windows PowerShell) pour configurer la valeur de la propriété ExchangeArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="1a987-193">Note that you must use the Lync Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="1a987-194">Cette propriété n’est pas exposée aux administrateurs dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a987-194">This property is not exposed to administrators in the Lync Server Control Panel.</span></span>

<span data-ttu-id="1a987-195">Si vous voulez afficher la liste de tous les utilisateurs auxquels une stratégie spécifique a été attribuée, vous pouvez utiliser une commande semblable à la suivante, qui renvoie le nom d’affichage Active Directory de tous les utilisateurs dont la propriété ExchangeArchivingPolicy a la valeur Uninitialized :</span><span class="sxs-lookup"><span data-stu-id="1a987-195">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

<span data-ttu-id="1a987-196">De même, cette commande renvoie le nom d’affichage des utilisateurs dont la propriété ExchangeArchivingPolicy n’a pas la valeur UseLyncArchivingPolicy :</span><span class="sxs-lookup"><span data-stu-id="1a987-196">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

