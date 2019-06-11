---
title: Intégration d’une application de collaboration tierce avec Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b56fabbc1bd341e3ba2c5fe535d147c09335b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="6ea5c-102">Intégration d’une application de collaboration tierce avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ea5c-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ea5c-103">_**Dernière modification de la rubrique:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="6ea5c-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="6ea5c-104">Vous pouvez intégrer Lync 2013 à toute application de collaboration en ligne tierce en ajoutant des informations sur l’application au registre.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="6ea5c-105">Vous pouvez utiliser Lync 2013 pour démarrer des sessions de conférence de données hébergées sur un serveur interne, un service basé sur Internet, ou les deux.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="6ea5c-106">La session de collaboration ou de conférence de données peut être démarrée à partir de la liste de contacts ou à partir d’une conversation par messagerie instantanée, audio ou vidéo.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="6ea5c-107">Lync 2013 agit uniquement comme véhicule pour le démarrage de l’application.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="6ea5c-108">Toutes les conversations Lync 2013 existantes restent actives après le démarrage de la session de collaboration en ligne.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="6ea5c-109">Les sections suivantes décrivent comment intégrer Lync 2013 aux applications de collaboration basées sur Internet et celles basées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="6ea5c-110">Intégration d’une application de collaboration basée sur Internet avec Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6ea5c-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="6ea5c-111">En règle générale, les étapes nécessaires à l’intégration d’une application de collaboration tierce sont les suivantes:</span><span class="sxs-lookup"><span data-stu-id="6ea5c-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="6ea5c-112">Des informations sur l’application sont ajoutées au registre.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="6ea5c-113">L’organisateur se connecte à Lync 2013 et sélectionne les contacts pour le partage et la collaboration de données.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="6ea5c-114">Il est possible que l’organisateur se trouve déjà dans une conversation et décide d’ajouter des conférences de données.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="6ea5c-115">Lync 2013 lit le registre, démarre l’application de collaboration, puis envoie un message SIP personnalisé (appINVITE) aux participants sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="6ea5c-116">Les participants acceptent l’invitation et l’application de collaboration est démarrée sur l’ordinateur de chaque personne.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="6ea5c-117">Lync 2013 utilise le registre pour déterminer quelle application de collaboration utiliser, puis démarre cette application en utilisant les paramètres inclus dans le message appINVITE.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="6ea5c-118">Le tableau suivant décrit les entrées de Registre requises pour intégrer une application de collaboration basée sur Internet avec Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="6ea5c-119">Ces entrées sont placées dans le registre à l’emplacement suivant:</span><span class="sxs-lookup"><span data-stu-id="6ea5c-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="6ea5c-120">HKEY\_logiciel\_\\de\\l’ordinateur\\local\\Microsoft\\Office\\15,0\\les\\paramètres des applications Lync sessionmanager</span><span class="sxs-lookup"><span data-stu-id="6ea5c-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="6ea5c-121">Entrées de Registre pour une application de collaboration basée sur Internet</span><span class="sxs-lookup"><span data-stu-id="6ea5c-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ea5c-122">Nom</span><span class="sxs-lookup"><span data-stu-id="6ea5c-122">Name</span></span></th>
<th><span data-ttu-id="6ea5c-123">Type</span><span class="sxs-lookup"><span data-stu-id="6ea5c-123">Type</span></span></th>
<th><span data-ttu-id="6ea5c-124">Données</span><span class="sxs-lookup"><span data-stu-id="6ea5c-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ea5c-125">Nom</span><span class="sxs-lookup"><span data-stu-id="6ea5c-125">Name</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-127">Nom de l’application pour les menus Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ea5c-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="6ea5c-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-130">Chemin d’accès à l’icône 16 pixels x 16 pixels, BMP ou PNG.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ea5c-131"> Path</span><span class="sxs-lookup"><span data-stu-id="6ea5c-131">Path</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-133">Chemin du participant pour le démarrage de l’application de collaboration en ligne.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ea5c-134">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="6ea5c-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-136">Chemin d’accès de l’organisateur du démarrage de l’application de collaboration en ligne.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="6ea5c-137">Ce chemin peut contenir un ou plusieurs paramètres personnalisés tels qu’ils sont définis dans la sous-clé paramètres.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="6ea5c-138">Par exemple,<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="6ea5c-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ea5c-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="6ea5c-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-140">INSÉRÉ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-141">0 = session locale.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-141">0 = Local session.</span></span> <span data-ttu-id="6ea5c-142">L’application est démarrée sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-142">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="6ea5c-143">1 = session à deux parties (par défaut).</span><span class="sxs-lookup"><span data-stu-id="6ea5c-143">1 = Two-party session (default).</span></span> <span data-ttu-id="6ea5c-144">Lync 2013 démarre l’application localement, puis envoie une notification système à l’autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="6ea5c-145">L’autre utilisateur clique sur la notification et démarre l’application spécifiée sur son ordinateur.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="6ea5c-146">2 = session multipartie.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-146">2 = Multiparty session.</span></span> <span data-ttu-id="6ea5c-147">Lync 2013 démarre l’application localement, puis envoie des notifications système aux autres utilisateurs, en leur demandant de démarrer l’application spécifiée sur leur ordinateur.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ea5c-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="6ea5c-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-150">Liste des menus dans lesquels cette commande s’affiche, séparés par des points-virgules.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-150">A list of the menus where this command will appear, separated by semi-colons.</span></span> <span data-ttu-id="6ea5c-151">Valeurs possibles :</span><span class="sxs-lookup"><span data-stu-id="6ea5c-151">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6ea5c-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="6ea5c-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="6ea5c-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="6ea5c-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="6ea5c-154">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="6ea5c-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="6ea5c-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="6ea5c-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="6ea5c-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="6ea5c-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="6ea5c-157">Si ExtensibleMenu n’est pas défini, les valeurs par défaut de MainWindowRightClick et ConversationWindowActions sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6ea5c-158">Le tableau suivant décrit les entrées de Registre correspondant aux paramètres.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="6ea5c-159">Ces entrées sont placées sur\_HKEY\_logiciel\\\\de l'\\utilisateur\\actuel\\Microsoft\\Office\\15,0\\les paramètres des applications Lync sessionmanager.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="6ea5c-160">Entrées de Registre pour une application de collaboration basée sur Internet</span><span class="sxs-lookup"><span data-stu-id="6ea5c-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ea5c-161">Nom</span><span class="sxs-lookup"><span data-stu-id="6ea5c-161">Name</span></span></th>
<th><span data-ttu-id="6ea5c-162">Type</span><span class="sxs-lookup"><span data-stu-id="6ea5c-162">Type</span></span></th>
<th><span data-ttu-id="6ea5c-163">Données</span><span class="sxs-lookup"><span data-stu-id="6ea5c-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ea5c-164">TypeDonnées</span><span class="sxs-lookup"><span data-stu-id="6ea5c-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-166">Permet d’ajouter des valeurs spécifiques<code>%Parm1%</code>à l’utilisateur dans la clé de Registre OriginatorPath.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ea5c-167">TypeDonnées</span><span class="sxs-lookup"><span data-stu-id="6ea5c-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-169">Voir Param1.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ea5c-170">Param3</span><span class="sxs-lookup"><span data-stu-id="6ea5c-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-172">Voir Param1.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6ea5c-173">Les exemples de paramètres de registre suivants intègrent le client de collaboration adatum avec Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="6ea5c-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="6ea5c-174">Intégration d’une application de collaboration basée sur le serveur avec Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6ea5c-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="6ea5c-175">Les paramètres permettant d’ajouter des commandes pour le démarrage d’une application de collaboration serveur à partir de Lync 2013 sont similaires à ceux décrits dans la section précédente, intégration d’une application de collaboration basée sur Internet avec Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="6ea5c-176">Toutefois, le OriginatorPath n’est pas obligatoire et certaines valeurs sont modifiées.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="6ea5c-177">Les entrées de Registre sont placées à l’emplacement suivant:</span><span class="sxs-lookup"><span data-stu-id="6ea5c-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="6ea5c-178">HKEY\_logiciel\_\\de\\l’ordinateur\\local\\Microsoft\\Office\\15,0\\les\\paramètres des applications Lync sessionmanager</span><span class="sxs-lookup"><span data-stu-id="6ea5c-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="6ea5c-179">Entrées de Registre pour une application de collaboration basée sur le serveur</span><span class="sxs-lookup"><span data-stu-id="6ea5c-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ea5c-180">Nom</span><span class="sxs-lookup"><span data-stu-id="6ea5c-180">Name</span></span></th>
<th><span data-ttu-id="6ea5c-181">Type</span><span class="sxs-lookup"><span data-stu-id="6ea5c-181">Type</span></span></th>
<th><span data-ttu-id="6ea5c-182">Données</span><span class="sxs-lookup"><span data-stu-id="6ea5c-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ea5c-183">Nom</span><span class="sxs-lookup"><span data-stu-id="6ea5c-183">Name</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-185">Nom de l’application tel qu’il apparaît dans le menu.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ea5c-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="6ea5c-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-187">INSÉRÉ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-188">Valeur = 1.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-188">Value = 1.</span></span> <span data-ttu-id="6ea5c-189">Définit le type d’application sur protocole.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-189">Sets the application type to protocol.</span></span> <span data-ttu-id="6ea5c-190">Les autres valeurs possibles ne s’appliquent pas dans le cas présent.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="6ea5c-191">Si ce n’est pas le cas, ApplicationType est défini sur 0 (exécutable).</span><span class="sxs-lookup"><span data-stu-id="6ea5c-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ea5c-192"> Path</span><span class="sxs-lookup"><span data-stu-id="6ea5c-192">Path</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-194">Protocole utilisé pour démarrer l’application de collaboration.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="6ea5c-195">Pour Live Meeting 2007, la valeur de path est définie sur <code>meet:%conf-uri%</code>.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ea5c-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="6ea5c-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-197">INSÉRÉ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-198">0 = session locale.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-198">0 = Local session.</span></span> <span data-ttu-id="6ea5c-199">L’application est démarrée sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-199">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="6ea5c-200">1 = session à deux parties (par défaut).</span><span class="sxs-lookup"><span data-stu-id="6ea5c-200">1 = Two-party session (default).</span></span> <span data-ttu-id="6ea5c-201">Lync 2013 démarre l’application localement, puis envoie une notification système à l’autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="6ea5c-202">L’autre utilisateur clique sur la notification et démarre l’application spécifiée sur son ordinateur.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="6ea5c-203">2 = session multipartie.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-203">2 = Multiparty session.</span></span> <span data-ttu-id="6ea5c-204">Lync 2013 démarre l’application localement, puis envoie des notifications système aux autres utilisateurs, en leur demandant de démarrer l’application spécifiée sur leur ordinateur.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ea5c-205">MCUType</span><span class="sxs-lookup"><span data-stu-id="6ea5c-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-207">DATA = le type du serveur.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ea5c-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="6ea5c-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6ea5c-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="6ea5c-210">Liste des menus dans lesquels cette commande s’affiche, en les séparant par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="6ea5c-211">Valeurs possibles :</span><span class="sxs-lookup"><span data-stu-id="6ea5c-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6ea5c-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="6ea5c-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="6ea5c-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="6ea5c-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="6ea5c-214">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="6ea5c-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="6ea5c-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="6ea5c-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="6ea5c-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="6ea5c-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="6ea5c-217">Si ExtensibleMenu n’est pas défini, les valeurs par défaut de MainWindowRightClick et ConversationWindowActions sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="6ea5c-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6ea5c-218">L’exemple suivant ajoute des commandes pour démarrer le client de collaboration adatum à partir de Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="6ea5c-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

