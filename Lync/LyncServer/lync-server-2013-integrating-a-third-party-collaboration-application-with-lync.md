---
title: Intégration d’une application de collaboration tierce à Lync
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
ms.openlocfilehash: 9ae021735f5fec25cfaba625bd61460e9f58abb4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="82751-102">Intégration d’une application de collaboration tierce avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82751-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82751-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="82751-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="82751-104">Vous pouvez intégrer Lync 2013 avec n’importe quelle application de collaboration en ligne tierce en ajoutant des informations sur l’application au registre.</span><span class="sxs-lookup"><span data-stu-id="82751-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="82751-105">Vous pouvez utiliser Lync 2013 pour démarrer des sessions de conférence de données hébergées sur un serveur interne, un service basé sur Internet ou les deux.</span><span class="sxs-lookup"><span data-stu-id="82751-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="82751-106">Vous pouvez démarrer la session de collaboration ou de conférence de données directement à partir de la liste des contacts, ou bien à partir d’une session existante (vocale, messagerie instantanée ou vidéo).</span><span class="sxs-lookup"><span data-stu-id="82751-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="82751-107">Lync 2013 agit uniquement en tant que véhicule pour le démarrage de l’application.</span><span class="sxs-lookup"><span data-stu-id="82751-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="82751-108">Toute conversation Lync 2013 existante reste active après le début de la session de collaboration en ligne.</span><span class="sxs-lookup"><span data-stu-id="82751-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="82751-109">Les sections suivantes décrivent comment intégrer Lync 2013 avec des applications de collaboration basées sur Internet et sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="82751-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="82751-110">Intégration d’une application de collaboration basée sur Internet avec Lync 2013</span><span class="sxs-lookup"><span data-stu-id="82751-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="82751-111">En règle générale, les étapes requises pour l’intégration d’une application de collaboration tierce sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="82751-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="82751-112">Les informations relatives à l’application sont ajoutées au Registre.</span><span class="sxs-lookup"><span data-stu-id="82751-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="82751-113">L’organisateur se connecte à Lync 2013 et sélectionne les contacts pour le partage et la collaboration de données.</span><span class="sxs-lookup"><span data-stu-id="82751-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="82751-114">L’organisateur peut également ajouter une conférence de données à une conversation à laquelle il participe déjà.</span><span class="sxs-lookup"><span data-stu-id="82751-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="82751-115">Lync 2013 lit le registre, démarre l’application de collaboration, puis envoie un message SIP personnalisé, un appINVITE, aux participants sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="82751-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="82751-116">Les participants acceptent l’invitation et l’application de collaboration démarre sur l’ordinateur de chaque personne.</span><span class="sxs-lookup"><span data-stu-id="82751-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="82751-117">Lync 2013 utilise le registre pour déterminer l’application de collaboration à utiliser, puis démarre cette application en utilisant les paramètres inclus dans le message appINVITE.</span><span class="sxs-lookup"><span data-stu-id="82751-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="82751-118">Le tableau suivant décrit les entrées de Registre requises pour intégrer une application de collaboration basée sur Internet à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="82751-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="82751-119">Ces entrées sont placées dans le registre à l’emplacement suivant :</span><span class="sxs-lookup"><span data-stu-id="82751-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="82751-120">HKEY\_\\Software\_local Software\\Microsoft\\Office\\15,0\\Lync\\sessionmanager\\Apps\\Parameters</span><span class="sxs-lookup"><span data-stu-id="82751-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="82751-121">Entrées de Registre pour une application de collaboration basée sur Internet</span><span class="sxs-lookup"><span data-stu-id="82751-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82751-122">Nom</span><span class="sxs-lookup"><span data-stu-id="82751-122">Name</span></span></th>
<th><span data-ttu-id="82751-123">Type</span><span class="sxs-lookup"><span data-stu-id="82751-123">Type</span></span></th>
<th><span data-ttu-id="82751-124">Données</span><span class="sxs-lookup"><span data-stu-id="82751-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82751-125">Nom</span><span class="sxs-lookup"><span data-stu-id="82751-125">Name</span></span></p></td>
<td><p><span data-ttu-id="82751-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="82751-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="82751-127">Nom de l’application pour les menus Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="82751-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82751-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="82751-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="82751-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="82751-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="82751-130">Chemin d’accès de l’icône (BMP ou PNG de 16 pixels sur 16).</span><span class="sxs-lookup"><span data-stu-id="82751-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82751-131">Path</span><span class="sxs-lookup"><span data-stu-id="82751-131">Path</span></span></p></td>
<td><p><span data-ttu-id="82751-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="82751-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="82751-133">Chemin à utiliser pour le démarrage de l’application de collaboration en ligne sur l’ordinateur du participant.</span><span class="sxs-lookup"><span data-stu-id="82751-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82751-134">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="82751-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="82751-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="82751-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="82751-136">Chemin à utiliser pour le démarrage de l’application de collaboration en ligne par l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="82751-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="82751-137">Ce chemin peut contenir un ou plusieurs paramètres personnalisés définis dans la sous-clé Parameters.</span><span class="sxs-lookup"><span data-stu-id="82751-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="82751-138">Par exemple, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="82751-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82751-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="82751-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="82751-140">COMPLÉTER</span><span class="sxs-lookup"><span data-stu-id="82751-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="82751-p106">0 = Session locale. L’application démarre sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="82751-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="82751-143">1 = Session à deux personnes (par défaut).</span><span class="sxs-lookup"><span data-stu-id="82751-143">1 = Two-party session (default).</span></span> <span data-ttu-id="82751-144">Lync 2013 démarre l’application localement, puis envoie une notification système à l’autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="82751-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="82751-145">Ce dernier clique alors sur la notification pour démarrer l’application spécifiée sur son ordinateur.</span><span class="sxs-lookup"><span data-stu-id="82751-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="82751-146">2 = Session à plusieurs.</span><span class="sxs-lookup"><span data-stu-id="82751-146">2 = Multiparty session.</span></span> <span data-ttu-id="82751-147">Lync 2013 démarre l’application localement, puis envoie des notifications système aux autres utilisateurs, en les invitant à démarrer l’application spécifiée sur leur propre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="82751-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82751-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="82751-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="82751-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="82751-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="82751-p109">Liste des menus dans lesquels cette commande apparaîtra. Les menus sont séparés par un point-virgule. Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="82751-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="82751-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="82751-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="82751-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="82751-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="82751-154">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="82751-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="82751-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="82751-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="82751-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="82751-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="82751-157">Si ExtensibleMenu n’est pas défini, les valeurs par défaut de MainWindowRightClick et ConversationWindowActions sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="82751-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="82751-158">Le tableau suivant décrit les entrées de Registre pour les paramètres.</span><span class="sxs-lookup"><span data-stu-id="82751-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="82751-159">Ces entrées sont placées dans\_HKEY\_Current\\user\\Software\\Microsoft\\Office\\15,0\\Lync\\sessionmanager\\Apps Parameters.</span><span class="sxs-lookup"><span data-stu-id="82751-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="82751-160">Entrées de Registre pour une application de collaboration basée sur Internet</span><span class="sxs-lookup"><span data-stu-id="82751-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82751-161">Nom</span><span class="sxs-lookup"><span data-stu-id="82751-161">Name</span></span></th>
<th><span data-ttu-id="82751-162">Type</span><span class="sxs-lookup"><span data-stu-id="82751-162">Type</span></span></th>
<th><span data-ttu-id="82751-163">Données</span><span class="sxs-lookup"><span data-stu-id="82751-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82751-164">Param1</span><span class="sxs-lookup"><span data-stu-id="82751-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="82751-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="82751-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="82751-166">Utilisé dans le format sous forme<code>%Parm1%</code>de jeton () pour ajouter des valeurs spécifiques à l’utilisateur à la clé de Registre OriginatorPath.</span><span class="sxs-lookup"><span data-stu-id="82751-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82751-167">TypeDonnées</span><span class="sxs-lookup"><span data-stu-id="82751-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="82751-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="82751-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="82751-169">Voir Param1.</span><span class="sxs-lookup"><span data-stu-id="82751-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82751-170">Param3</span><span class="sxs-lookup"><span data-stu-id="82751-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="82751-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="82751-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="82751-172">Voir Param1.</span><span class="sxs-lookup"><span data-stu-id="82751-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="82751-173">Les exemples de paramètres de registre suivants intègrent le client de collaboration adatum avec Lync 2013 :</span><span class="sxs-lookup"><span data-stu-id="82751-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="82751-174">Intégration d’une application de collaboration basée sur un serveur avec Lync 2013</span><span class="sxs-lookup"><span data-stu-id="82751-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="82751-175">Les paramètres permettant d’ajouter des commandes de démarrage d’une application de collaboration basée sur un serveur à partir de Lync 2013 sont semblables à ceux décrits dans la section précédente, intégrant une application de collaboration basée sur Internet à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="82751-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="82751-176">Toutefois, OriginatorPath n’est pas requis et certaines valeurs changent.</span><span class="sxs-lookup"><span data-stu-id="82751-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="82751-177">Les entrées de Registre sont placées à l’emplacement suivant :</span><span class="sxs-lookup"><span data-stu-id="82751-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="82751-178">HKEY\_\\Software\_local Software\\Microsoft\\Office\\15,0\\Lync\\sessionmanager\\Apps\\Parameters</span><span class="sxs-lookup"><span data-stu-id="82751-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="82751-179">Entrées de Registre pour une application de collaboration basée sur un serveur</span><span class="sxs-lookup"><span data-stu-id="82751-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82751-180">Nom</span><span class="sxs-lookup"><span data-stu-id="82751-180">Name</span></span></th>
<th><span data-ttu-id="82751-181">Type</span><span class="sxs-lookup"><span data-stu-id="82751-181">Type</span></span></th>
<th><span data-ttu-id="82751-182">Données</span><span class="sxs-lookup"><span data-stu-id="82751-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82751-183">Nom</span><span class="sxs-lookup"><span data-stu-id="82751-183">Name</span></span></p></td>
<td><p><span data-ttu-id="82751-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="82751-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="82751-185">Nom de l’application tel qu’il apparaît dans le menu.</span><span class="sxs-lookup"><span data-stu-id="82751-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82751-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="82751-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="82751-187">COMPLÉTER</span><span class="sxs-lookup"><span data-stu-id="82751-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="82751-188">Valeur = 1.</span><span class="sxs-lookup"><span data-stu-id="82751-188">Value = 1.</span></span> <span data-ttu-id="82751-189">Définit le type de l’application comme protocole.</span><span class="sxs-lookup"><span data-stu-id="82751-189">Sets the application type to protocol.</span></span> <span data-ttu-id="82751-190">Les autres valeurs possibles ne sont pas applicables dans ce cas.</span><span class="sxs-lookup"><span data-stu-id="82751-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="82751-191">S’il n’est pas présent, ApplicationType est défini sur 0 (exécutable).</span><span class="sxs-lookup"><span data-stu-id="82751-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82751-192">Path</span><span class="sxs-lookup"><span data-stu-id="82751-192">Path</span></span></p></td>
<td><p><span data-ttu-id="82751-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="82751-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="82751-194">Protocole utilisé pour démarrer l’application de collaboration.</span><span class="sxs-lookup"><span data-stu-id="82751-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="82751-195">Pour Live Meeting 2007, la valeur de path est définie sur <code>meet:%conf-uri%</code>.</span><span class="sxs-lookup"><span data-stu-id="82751-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82751-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="82751-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="82751-197">COMPLÉTER</span><span class="sxs-lookup"><span data-stu-id="82751-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="82751-p114">0 = Session locale. L’application démarre sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="82751-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="82751-200">1 = Session à deux personnes (par défaut).</span><span class="sxs-lookup"><span data-stu-id="82751-200">1 = Two-party session (default).</span></span> <span data-ttu-id="82751-201">Lync 2013 démarre l’application localement, puis envoie une notification système à l’autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="82751-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="82751-202">Ce dernier clique alors sur la notification pour démarrer l’application spécifiée sur son ordinateur.</span><span class="sxs-lookup"><span data-stu-id="82751-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="82751-203">2 = Session à plusieurs.</span><span class="sxs-lookup"><span data-stu-id="82751-203">2 = Multiparty session.</span></span> <span data-ttu-id="82751-204">Lync 2013 démarre l’application localement, puis envoie des notifications système aux autres utilisateurs, en les invitant à démarrer l’application spécifiée sur leur ordinateur.</span><span class="sxs-lookup"><span data-stu-id="82751-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82751-205">MCUType</span><span class="sxs-lookup"><span data-stu-id="82751-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="82751-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="82751-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="82751-207">DATA = Type du serveur.</span><span class="sxs-lookup"><span data-stu-id="82751-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82751-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="82751-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="82751-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="82751-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="82751-210">Liste des menus dans lesquels cette commande apparaît, séparés par des points-virgules.</span><span class="sxs-lookup"><span data-stu-id="82751-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="82751-211">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="82751-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="82751-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="82751-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="82751-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="82751-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="82751-214">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="82751-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="82751-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="82751-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="82751-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="82751-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="82751-217">Si ExtensibleMenu n’est pas défini, les valeurs par défaut de MainWindowRightClick et ConversationWindowActions sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="82751-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="82751-218">L’exemple suivant ajoute des commandes pour démarrer le client de collaboration adatum à partir de Lync 2013 :</span><span class="sxs-lookup"><span data-stu-id="82751-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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

