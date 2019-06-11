---
title: 'Lync Server 2013: ajout de commandes aux menus Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dfb79a985791e6994d8409339d12b12e1146ec5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="a5e2e-102">Ajouter des commandes aux menus Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5e2e-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5e2e-103">_**Dernière modification de la rubrique:** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="a5e2e-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="a5e2e-104">Vous pouvez ajouter des commandes personnalisées aux menus de Lync 2013 et transmettre l’URI (Uniform Resource Identifier) SIP de l’utilisateur actuel et des contacts sélectionnés à l’application qui démarre la commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="a5e2e-105">Les commandes personnalisées que vous ajoutez peuvent apparaître dans un ou plusieurs des menus suivants:</span><span class="sxs-lookup"><span data-stu-id="a5e2e-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="a5e2e-106">Menu Outils, dans la barre de menus de la fenêtre principale de Lync</span><span class="sxs-lookup"><span data-stu-id="a5e2e-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="a5e2e-107">Menu contextuel des contacts de la liste de contacts</span><span class="sxs-lookup"><span data-stu-id="a5e2e-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="a5e2e-108">Menu autres options, dans la fenêtre de conversation</span><span class="sxs-lookup"><span data-stu-id="a5e2e-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="a5e2e-109">Menu contextuel pour les personnes figurant dans la liste des participants de la fenêtre de conversation</span><span class="sxs-lookup"><span data-stu-id="a5e2e-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="a5e2e-110">Menu options dans une carte de visite</span><span class="sxs-lookup"><span data-stu-id="a5e2e-110">The options menu in a contact card</span></span>

<span data-ttu-id="a5e2e-111">Vous pouvez définir des commandes personnalisées pour deux types d’applications (applications qui effectuent l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="a5e2e-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="a5e2e-112">S’applique uniquement à l’utilisateur actuel et est démarré sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="a5e2e-113">Impliquez des utilisateurs supplémentaires, tels qu’un programme de collaboration en ligne, qui doivent être démarrés sur l’ordinateur de chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="a5e2e-114">La commande personnalisée peut être appelée de l’une des façons suivantes:</span><span class="sxs-lookup"><span data-stu-id="a5e2e-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="a5e2e-115">Sélectionnez un ou plusieurs utilisateurs, puis choisissez la commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="a5e2e-116">Démarrer une conversation à deux ou plusieurs parties, puis sélectionner la commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="a5e2e-117">Pour ajouter une commande personnalisée</span><span class="sxs-lookup"><span data-stu-id="a5e2e-117">To add a custom command</span></span>

<span data-ttu-id="a5e2e-118">Utilisez les paramètres de Registre du tableau suivant pour ajouter une commande aux menus.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="a5e2e-119">Ces entrées sont placées dans le registre à l’un des emplacements suivants:</span><span class="sxs-lookup"><span data-stu-id="a5e2e-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="a5e2e-120">Pour le système d’exploitation\_32\_bits\\:\\HKEY\\logiciel\\de\\l'\\ordinateur\\local Microsoft Office 15,0 des applications Lync sessionmanager</span><span class="sxs-lookup"><span data-stu-id="a5e2e-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="a5e2e-121">Pour les systèmes d’exploitation\_64\_bits\\:\\HKEY\\logiciel\\de\\l'\\ordinateur\\local\\Wow6432Node Microsoft Office 15,0 Lync sessionmanager apps</span><span class="sxs-lookup"><span data-stu-id="a5e2e-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="a5e2e-122">Entrées de registre de commandes personnalisées</span><span class="sxs-lookup"><span data-stu-id="a5e2e-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5e2e-123">Nom</span><span class="sxs-lookup"><span data-stu-id="a5e2e-123">Name</span></span></th>
<th><span data-ttu-id="a5e2e-124">Type</span><span class="sxs-lookup"><span data-stu-id="a5e2e-124">Type</span></span></th>
<th><span data-ttu-id="a5e2e-125">Données</span><span class="sxs-lookup"><span data-stu-id="a5e2e-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5e2e-126">Nom</span><span class="sxs-lookup"><span data-stu-id="a5e2e-126">Name</span></span></p></td>
<td><p><span data-ttu-id="a5e2e-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e2e-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="a5e2e-128">Nom de l’application tel qu’il apparaît dans le menu.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5e2e-129">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="a5e2e-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="a5e2e-130">INSÉRÉ</span><span class="sxs-lookup"><span data-stu-id="a5e2e-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="a5e2e-131">0 = exécutable (par défaut)</span><span class="sxs-lookup"><span data-stu-id="a5e2e-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a5e2e-132">Nécessite ApplicationInstallPath.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="a5e2e-133">1 = Protocole</span><span class="sxs-lookup"><span data-stu-id="a5e2e-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5e2e-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="a5e2e-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="a5e2e-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e2e-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="a5e2e-136">Chemin d’accès complet du fichier exécutable.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a5e2e-137">Doit être spécifié si ApplicationType est défini sur 0 (exécutable).</span><span class="sxs-lookup"><span data-stu-id="a5e2e-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5e2e-138"> Path</span><span class="sxs-lookup"><span data-stu-id="a5e2e-138">Path</span></span></p></td>
<td><p><span data-ttu-id="a5e2e-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e2e-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="a5e2e-140">Chemin complet pour démarrer avec tout autre paramètre, y compris les paramètres par défaut <em>% User-ID%</em> et% <em>contact-ID%</em>.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5e2e-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="a5e2e-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="a5e2e-142">INSÉRÉ</span><span class="sxs-lookup"><span data-stu-id="a5e2e-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="a5e2e-143">0 = session locale.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-143">0 = Local session.</span></span> <span data-ttu-id="a5e2e-144">L’application est démarrée sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-144">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="a5e2e-145">1 = session à deux parties (par défaut).</span><span class="sxs-lookup"><span data-stu-id="a5e2e-145">1 = Two-party session (default).</span></span> <span data-ttu-id="a5e2e-146">Lync 2013 démarre l’application localement, puis envoie une notification de bureau à l’autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="a5e2e-147">L’autre utilisateur clique sur la notification pour démarrer l’application sur son ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="a5e2e-148">2 = session multipartie.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-148">2 = Multiparty session.</span></span> <span data-ttu-id="a5e2e-149">Lync 2013 démarre l’application localement, puis envoie des notifications de bureau aux autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="a5e2e-150">L’autre utilisateur clique sur la notification pour démarrer l’application spécifiée sur son ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5e2e-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="a5e2e-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="a5e2e-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a5e2e-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="a5e2e-153">Liste des menus dans lesquels cette commande s’affiche, en les séparant par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="a5e2e-154">Valeurs possibles :</span><span class="sxs-lookup"><span data-stu-id="a5e2e-154">Possible values are:</span></span></p>
<p><span data-ttu-id="a5e2e-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="a5e2e-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="a5e2e-156">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="a5e2e-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="a5e2e-157">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="a5e2e-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="a5e2e-158">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="a5e2e-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="a5e2e-159">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="a5e2e-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="a5e2e-160">Si ExtensibleMenu n’est pas défini, les valeurs par défaut de MainWindowRightClick et ConversationWindowActions sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a5e2e-161">Par exemple, l’éditeur du Registre suivant (. REG) affiche les résultats de l’ajout d’un élément de menu du gestionnaire de contacts commerciaux contoso au menu actions dans la fenêtre de conversation:</span><span class="sxs-lookup"><span data-stu-id="a5e2e-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a><span data-ttu-id="a5e2e-162">Pour accéder à une commande personnalisée</span><span class="sxs-lookup"><span data-stu-id="a5e2e-162">To access a custom command</span></span>

<span data-ttu-id="a5e2e-163">Pour accéder à une commande personnalisée après l’avoir ajoutée, effectuez l’une des opérations suivantes, en fonction des valeurs ExtensibleMenu que vous définissez:</span><span class="sxs-lookup"><span data-stu-id="a5e2e-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="a5e2e-164">**MainWindowActions**   dans la fenêtre principale de Lync, cliquez sur **Outils**, puis sur votre commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="a5e2e-165">**MainWindowRightClick**   dans la fenêtre principale de Lync, cliquez avec le bouton droit sur un contact, puis cliquez sur votre commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="a5e2e-166">**ConversationWindowActions**   dans la fenêtre de conversation, cliquez sur l’icône **plus d’options** , puis cliquez sur votre commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="a5e2e-167">**ConversationWindowRightClick**   dans la fenêtre de conversation, cliquez avec le bouton droit sur le nom d’un contact, puis cliquez sur votre commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="a5e2e-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

