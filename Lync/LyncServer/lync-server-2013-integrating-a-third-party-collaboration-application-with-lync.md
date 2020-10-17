---
title: Intégration d’une application de collaboration tierce à Lync
description: Intégration d’une application de collaboration tierce à Lync.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7adbe1abab83a569f581af034fc46abfef4cf819
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552650"
---
# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="eb4f9-103">Intégration d’une application de collaboration tierce avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb4f9-103">Integrating a third-party collaboration application with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb4f9-104">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="eb4f9-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="eb4f9-105">Vous pouvez intégrer Lync 2013 avec n’importe quelle application de collaboration en ligne tierce en ajoutant des informations sur l’application au registre.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-105">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="eb4f9-106">Vous pouvez utiliser Lync 2013 pour démarrer des sessions de conférence de données hébergées sur un serveur interne, un service basé sur Internet ou les deux.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-106">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="eb4f9-107">Vous pouvez démarrer la session de collaboration ou de conférence de données directement à partir de la liste des contacts, ou bien à partir d’une session existante (vocale, messagerie instantanée ou vidéo).</span><span class="sxs-lookup"><span data-stu-id="eb4f9-107">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="eb4f9-108">Lync 2013 agit uniquement en tant que véhicule pour le démarrage de l’application.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-108">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="eb4f9-109">Toute conversation Lync 2013 existante reste active après le début de la session de collaboration en ligne.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-109">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="eb4f9-110">Les sections suivantes décrivent comment intégrer Lync 2013 avec des applications de collaboration basées sur Internet et sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-110">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="eb4f9-111">Intégration d’une application de collaboration Internet-Based avec Lync 2013</span><span class="sxs-lookup"><span data-stu-id="eb4f9-111">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="eb4f9-112">En règle générale, les étapes requises pour l’intégration d’une application de collaboration tierce sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="eb4f9-112">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="eb4f9-113">Les informations relatives à l’application sont ajoutées au Registre.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-113">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="eb4f9-114">L’organisateur se connecte à Lync 2013 et sélectionne les contacts pour le partage et la collaboration de données.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-114">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="eb4f9-115">L’organisateur peut également ajouter une conférence de données à une conversation à laquelle il participe déjà.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-115">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="eb4f9-116">Lync 2013 lit le registre, démarre l’application de collaboration, puis envoie un message SIP personnalisé, un appINVITE, aux participants sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-116">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="eb4f9-117">Les participants acceptent l’invitation et l’application de collaboration démarre sur l’ordinateur de chaque personne.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-117">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="eb4f9-118">Lync 2013 utilise le registre pour déterminer l’application de collaboration à utiliser, puis démarre cette application en utilisant les paramètres inclus dans le message appINVITE.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-118">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="eb4f9-119">Le tableau suivant décrit les entrées de Registre requises pour intégrer une application de collaboration basée sur Internet à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-119">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="eb4f9-120">Ces entrées sont placées dans le registre à l’emplacement suivant :</span><span class="sxs-lookup"><span data-stu-id="eb4f9-120">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="eb4f9-121">HKEY \_ \_ Software local \\ Software \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ sessionmanager \\ apps \\ Parameters</span><span class="sxs-lookup"><span data-stu-id="eb4f9-121">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="eb4f9-122">Entrées de Registre pour une application de collaboration basée sur Internet</span><span class="sxs-lookup"><span data-stu-id="eb4f9-122">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb4f9-123">Nom</span><span class="sxs-lookup"><span data-stu-id="eb4f9-123">Name</span></span></th>
<th><span data-ttu-id="eb4f9-124">Type</span><span class="sxs-lookup"><span data-stu-id="eb4f9-124">Type</span></span></th>
<th><span data-ttu-id="eb4f9-125">Données</span><span class="sxs-lookup"><span data-stu-id="eb4f9-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb4f9-126">Nom</span><span class="sxs-lookup"><span data-stu-id="eb4f9-126">Name</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eb4f9-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-128">Nom de l’application pour les menus Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-128">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb4f9-129">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="eb4f9-129">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-130">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eb4f9-130">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-131">Chemin d’accès de l’icône (BMP ou PNG de 16 pixels sur 16).</span><span class="sxs-lookup"><span data-stu-id="eb4f9-131">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb4f9-132">Path</span><span class="sxs-lookup"><span data-stu-id="eb4f9-132">Path</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-133">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eb4f9-133">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-134">Chemin à utiliser pour le démarrage de l’application de collaboration en ligne sur l’ordinateur du participant.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-134">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb4f9-135">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="eb4f9-135">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-136">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eb4f9-136">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-137">Chemin à utiliser pour le démarrage de l’application de collaboration en ligne par l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-137">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="eb4f9-138">Ce chemin peut contenir un ou plusieurs paramètres personnalisés définis dans la sous-clé Parameters.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-138">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="eb4f9-139">Par exemple, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="eb4f9-139">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb4f9-140">SessionType</span><span class="sxs-lookup"><span data-stu-id="eb4f9-140">SessionType</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-141">DWORD</span><span class="sxs-lookup"><span data-stu-id="eb4f9-141">DWORD</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-p106">0 = Session locale. L’application démarre sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="eb4f9-144">1 = Session à deux personnes (par défaut).</span><span class="sxs-lookup"><span data-stu-id="eb4f9-144">1 = Two-party session (default).</span></span> <span data-ttu-id="eb4f9-145">Lync 2013 démarre l’application localement, puis envoie une notification système à l’autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-145">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="eb4f9-146">Ce dernier clique alors sur la notification pour démarrer l’application spécifiée sur son ordinateur.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-146">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="eb4f9-147">2 = Session à plusieurs.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-147">2 = Multiparty session.</span></span> <span data-ttu-id="eb4f9-148">Lync 2013 démarre l’application localement, puis envoie des notifications système aux autres utilisateurs, en les invitant à démarrer l’application spécifiée sur leur propre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-148">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb4f9-149">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="eb4f9-149">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-150">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eb4f9-150">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-p109">Liste des menus dans lesquels cette commande apparaîtra. Les menus sont séparés par un point-virgule. Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="eb4f9-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb4f9-153">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="eb4f9-153">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="eb4f9-154">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="eb4f9-154">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="eb4f9-155">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="eb4f9-155">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="eb4f9-156">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="eb4f9-156">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="eb4f9-157">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="eb4f9-157">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="eb4f9-158">Si ExtensibleMenu n’est pas défini, les valeurs par défaut de MainWindowRightClick et ConversationWindowActions sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-158">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eb4f9-159">Le tableau suivant décrit les entrées de Registre pour les paramètres.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-159">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="eb4f9-160">Ces entrées sont placées dans HKEY \_ Current \_ User \\ Software \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ sessionmanager \\ apps \\ Parameters.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-160">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="eb4f9-161">Entrées de Registre pour une application de collaboration basée sur Internet</span><span class="sxs-lookup"><span data-stu-id="eb4f9-161">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb4f9-162">Nom</span><span class="sxs-lookup"><span data-stu-id="eb4f9-162">Name</span></span></th>
<th><span data-ttu-id="eb4f9-163">Type</span><span class="sxs-lookup"><span data-stu-id="eb4f9-163">Type</span></span></th>
<th><span data-ttu-id="eb4f9-164">Données</span><span class="sxs-lookup"><span data-stu-id="eb4f9-164">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb4f9-165">Param1</span><span class="sxs-lookup"><span data-stu-id="eb4f9-165">Param1</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-166">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eb4f9-166">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-167">Utilisé dans le format sous forme de jeton ( <code>%Parm1%</code> ) pour ajouter des valeurs spécifiques à l’utilisateur à la clé de Registre OriginatorPath.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-167">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb4f9-168">TypeDonnées</span><span class="sxs-lookup"><span data-stu-id="eb4f9-168">Param2</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-169">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eb4f9-169">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-170">Voir Param1.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-170">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb4f9-171">Param3</span><span class="sxs-lookup"><span data-stu-id="eb4f9-171">Param3</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-172">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eb4f9-172">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-173">Voir Param1.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-173">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eb4f9-174">Les exemples de paramètres de registre suivants intègrent le client de collaboration adatum avec Lync 2013 :</span><span class="sxs-lookup"><span data-stu-id="eb4f9-174">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="eb4f9-175">Intégration d’une application de collaboration Server-Based avec Lync 2013</span><span class="sxs-lookup"><span data-stu-id="eb4f9-175">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="eb4f9-176">Les paramètres permettant d’ajouter des commandes de démarrage d’une application de collaboration basée sur un serveur à partir de Lync 2013 sont similaires à ceux décrits dans la section précédente, intégrant une application de collaboration Internet-Based avec Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-176">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="eb4f9-177">Toutefois, OriginatorPath n’est pas requis et certaines valeurs changent.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-177">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="eb4f9-178">Les entrées de Registre sont placées à l’emplacement suivant :</span><span class="sxs-lookup"><span data-stu-id="eb4f9-178">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="eb4f9-179">HKEY \_ \_ Software local \\ Software \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ sessionmanager \\ apps \\ Parameters</span><span class="sxs-lookup"><span data-stu-id="eb4f9-179">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="eb4f9-180">Entrées de Registre pour une application de collaboration basée sur un serveur</span><span class="sxs-lookup"><span data-stu-id="eb4f9-180">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb4f9-181">Nom</span><span class="sxs-lookup"><span data-stu-id="eb4f9-181">Name</span></span></th>
<th><span data-ttu-id="eb4f9-182">Type</span><span class="sxs-lookup"><span data-stu-id="eb4f9-182">Type</span></span></th>
<th><span data-ttu-id="eb4f9-183">Données</span><span class="sxs-lookup"><span data-stu-id="eb4f9-183">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb4f9-184">Nom</span><span class="sxs-lookup"><span data-stu-id="eb4f9-184">Name</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eb4f9-185">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-186">Nom de l’application tel qu’il apparaît dans le menu.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-186">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb4f9-187">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="eb4f9-187">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-188">DWORD</span><span class="sxs-lookup"><span data-stu-id="eb4f9-188">DWORD</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-189">Valeur = 1.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-189">Value = 1.</span></span> <span data-ttu-id="eb4f9-190">Définit le type de l’application comme protocole.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-190">Sets the application type to protocol.</span></span> <span data-ttu-id="eb4f9-191">Les autres valeurs possibles ne sont pas applicables dans ce cas.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-191">The other possible values do not apply in this case.</span></span> <span data-ttu-id="eb4f9-192">S’il n’est pas présent, ApplicationType est défini sur 0 (exécutable).</span><span class="sxs-lookup"><span data-stu-id="eb4f9-192">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb4f9-193">Path</span><span class="sxs-lookup"><span data-stu-id="eb4f9-193">Path</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eb4f9-194">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-195">Protocole utilisé pour démarrer l’application de collaboration.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-195">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="eb4f9-196">Pour Live Meeting 2007, la valeur de path est définie sur <code>meet:%conf-uri%</code> .</span><span class="sxs-lookup"><span data-stu-id="eb4f9-196">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb4f9-197">SessionType</span><span class="sxs-lookup"><span data-stu-id="eb4f9-197">SessionType</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-198">DWORD</span><span class="sxs-lookup"><span data-stu-id="eb4f9-198">DWORD</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-p114">0 = Session locale. L’application démarre sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="eb4f9-201">1 = Session à deux personnes (par défaut).</span><span class="sxs-lookup"><span data-stu-id="eb4f9-201">1 = Two-party session (default).</span></span> <span data-ttu-id="eb4f9-202">Lync 2013 démarre l’application localement, puis envoie une notification système à l’autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-202">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="eb4f9-203">Ce dernier clique alors sur la notification pour démarrer l’application spécifiée sur son ordinateur.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-203">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="eb4f9-204">2 = Session à plusieurs.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-204">2 = Multiparty session.</span></span> <span data-ttu-id="eb4f9-205">Lync 2013 démarre l’application localement, puis envoie des notifications système aux autres utilisateurs, en les invitant à démarrer l’application spécifiée sur leur ordinateur.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-205">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb4f9-206">MCUType</span><span class="sxs-lookup"><span data-stu-id="eb4f9-206">MCUType</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-207">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eb4f9-207">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-208">DATA = Type du serveur.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-208">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb4f9-209">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="eb4f9-209">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-210">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eb4f9-210">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eb4f9-211">Liste des menus dans lesquels cette commande apparaît, séparés par des points-virgules.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-211">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="eb4f9-212">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="eb4f9-212">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb4f9-213">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="eb4f9-213">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="eb4f9-214">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="eb4f9-214">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="eb4f9-215">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="eb4f9-215">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="eb4f9-216">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="eb4f9-216">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="eb4f9-217">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="eb4f9-217">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="eb4f9-218">Si ExtensibleMenu n’est pas défini, les valeurs par défaut de MainWindowRightClick et ConversationWindowActions sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-218">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eb4f9-219">L’exemple suivant ajoute des commandes pour démarrer le client de collaboration adatum à partir de Lync 2013 :</span><span class="sxs-lookup"><span data-stu-id="eb4f9-219">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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

