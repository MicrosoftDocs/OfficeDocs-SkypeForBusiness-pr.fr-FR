---
title: 'Lync Server 2013 : ajout de commandes aux menus de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b6377824a7d96e6bb7b0ae6c60c79f3ee4c05b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="0b5e3-102">Ajout de commandes aux menus Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b5e3-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b5e3-103">_**Dernière modification de la rubrique :** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="0b5e3-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="0b5e3-104">Vous pouvez ajouter des commandes personnalisées aux menus Lync 2013 et transmettre l’URI (Uniform Resource Identifier) SIP de l’utilisateur actuel et des contacts sélectionnés à l’application de démarrage de la commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="0b5e3-105">Les commandes personnalisées que vous ajoutez peuvent apparaître sur un ou plusieurs des menus suivants :</span><span class="sxs-lookup"><span data-stu-id="0b5e3-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="0b5e3-106">Le menu Outils, sur la barre de menus dans la fenêtre principale Lync</span><span class="sxs-lookup"><span data-stu-id="0b5e3-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="0b5e3-107">Le menu contextuel pour les contacts dans la liste des contacts</span><span class="sxs-lookup"><span data-stu-id="0b5e3-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="0b5e3-108">Menu autres options, dans la fenêtre de conversation</span><span class="sxs-lookup"><span data-stu-id="0b5e3-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="0b5e3-109">Le menu contextuel pour les personnes mentionnées sur la liste des participants dans la fenêtre de conversation</span><span class="sxs-lookup"><span data-stu-id="0b5e3-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="0b5e3-110">Le menu options dans une carte de visite</span><span class="sxs-lookup"><span data-stu-id="0b5e3-110">The options menu in a contact card</span></span>

<span data-ttu-id="0b5e3-111">Vous pouvez définir des commandes personnalisées pour deux types d'applications possédant une des caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="0b5e3-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="0b5e3-112">S’appliquer uniquement à l’utilisateur actuel et être lancées sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="0b5e3-113">Englober des utilisateurs supplémentaires, comme par exemple un programme de collaboration en ligne, et devant être lancées sur l’ordinateur de chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="0b5e3-114">La commande personnalisée peut être appelée des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="0b5e3-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="0b5e3-115">Sélectionner un ou plusieurs utilisateurs puis choisir la commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="0b5e3-116">Commencer une conversation entre deux ou plusieurs parties, puis choisir la commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="0b5e3-117">Pour ajouter une commande personnalisée</span><span class="sxs-lookup"><span data-stu-id="0b5e3-117">To add a custom command</span></span>

<span data-ttu-id="0b5e3-118">Utilisez les paramètres de Registre du tableau suivant pour ajouter une commande aux menus.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="0b5e3-119">Ces entrées sont placées dans le registre à l’un des emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="0b5e3-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="0b5e3-120">Pour le système d’exploitation\_32\_bits\\:\\le\\logiciel\\Microsoft\\Office\\15,0\\Lync sessionmanager apps de l’ordinateur local</span><span class="sxs-lookup"><span data-stu-id="0b5e3-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="0b5e3-121">Pour 64 bits : HKEY\_Software\_\\\\local machine Wow6432Node\\Microsoft\\Office\\15,0\\Lync\\sessionmanager\\apps</span><span class="sxs-lookup"><span data-stu-id="0b5e3-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="0b5e3-122">Entrées du registre de commandes personnalisées</span><span class="sxs-lookup"><span data-stu-id="0b5e3-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b5e3-123">Nom</span><span class="sxs-lookup"><span data-stu-id="0b5e3-123">Name</span></span></th>
<th><span data-ttu-id="0b5e3-124">Type</span><span class="sxs-lookup"><span data-stu-id="0b5e3-124">Type</span></span></th>
<th><span data-ttu-id="0b5e3-125">Données</span><span class="sxs-lookup"><span data-stu-id="0b5e3-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b5e3-126">Nom</span><span class="sxs-lookup"><span data-stu-id="0b5e3-126">Name</span></span></p></td>
<td><p><span data-ttu-id="0b5e3-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="0b5e3-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="0b5e3-128">Nom de l’application tel qu’il apparaît dans le menu.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b5e3-129">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="0b5e3-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="0b5e3-130">COMPLÉTER</span><span class="sxs-lookup"><span data-stu-id="0b5e3-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="0b5e3-131">0 = exécutable (par défaut)</span><span class="sxs-lookup"><span data-stu-id="0b5e3-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0b5e3-132">Requiert ApplicationInstallPath.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="0b5e3-133">1 = protocole</span><span class="sxs-lookup"><span data-stu-id="0b5e3-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b5e3-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="0b5e3-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="0b5e3-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="0b5e3-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="0b5e3-136">Chemin d’accès complet de l’exécutable.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0b5e3-137">Doit être spécifié si l’ApplicationType est 0 (exécutable).</span><span class="sxs-lookup"><span data-stu-id="0b5e3-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b5e3-138">Path</span><span class="sxs-lookup"><span data-stu-id="0b5e3-138">Path</span></span></p></td>
<td><p><span data-ttu-id="0b5e3-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="0b5e3-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="0b5e3-140">Chemin d’accès complet à lancer avec des paramètres, y compris les paramètres par défaut <em>%user-id%</em> et <em>%contact-id%</em>.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b5e3-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="0b5e3-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="0b5e3-142">COMPLÉTER</span><span class="sxs-lookup"><span data-stu-id="0b5e3-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="0b5e3-p102">0 = Session locale. L’application démarre sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-p102">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="0b5e3-145">1 = Session à deux personnes (par défaut).</span><span class="sxs-lookup"><span data-stu-id="0b5e3-145">1 = Two-party session (default).</span></span> <span data-ttu-id="0b5e3-146">Lync 2013 démarre l’application localement, puis envoie une notification de bureau à l’autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="0b5e3-147">Ce dernier clique alors sur la notification pour lancer l’application spécifiée sur son ordinateur.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="0b5e3-148">2 = Session à plusieurs.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-148">2 = Multiparty session.</span></span> <span data-ttu-id="0b5e3-149">Lync 2013 démarre l’application localement, puis envoie des notifications de bureau aux autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="0b5e3-150">L’autre utilisateur clique sur la notification pour démarrer l’application spécifiée sur son ordinateur.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b5e3-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="0b5e3-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="0b5e3-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="0b5e3-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="0b5e3-153">Liste des menus dans lesquels cette commande apparaît, séparés par des points-virgules.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="0b5e3-154">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="0b5e3-154">Possible values are:</span></span></p>
<p><span data-ttu-id="0b5e3-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="0b5e3-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="0b5e3-156">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="0b5e3-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="0b5e3-157">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="0b5e3-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="0b5e3-158">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="0b5e3-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="0b5e3-159">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="0b5e3-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="0b5e3-160">Si ExtensibleMenu n’est pas défini, les valeurs par défaut de MainWindowRightClick et ConversationWindowActions sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0b5e3-161">Par exemple, le fichier suivant de l’Editeur du Registre (.REG) montre les résultats de l'addition d'un point de menu Gestionnaire de contacts vente Contoso à un menu Actions dans la fenêtre de conversation :</span><span class="sxs-lookup"><span data-stu-id="0b5e3-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

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

## <a name="to-access-a-custom-command"></a><span data-ttu-id="0b5e3-162">Pour accéder à une commande personnalisée</span><span class="sxs-lookup"><span data-stu-id="0b5e3-162">To access a custom command</span></span>

<span data-ttu-id="0b5e3-163">Pour accéder à une commande personnalisée une fois qu’elle a été ajoutée, effectuez l’une des opérations suivantes, en fonction des valeurs ExtensibleMenu que vous définissez :</span><span class="sxs-lookup"><span data-stu-id="0b5e3-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="0b5e3-164">**MainWindowActions**   dans la fenêtre principale Lync, cliquez sur **Outils**, puis sur votre commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="0b5e3-165">**MainWindowRightClick**   dans la fenêtre principale Lync, cliquez avec le bouton droit sur un contact, puis cliquez sur votre commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="0b5e3-166">**ConversationWindowActions**   dans la fenêtre de conversation, cliquez sur l’icône **autres options** , puis sur votre commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="0b5e3-167">**ConversationWindowRightClick**   dans la fenêtre de conversation, cliquez avec le bouton droit sur le nom d’un contact, puis cliquez sur votre commande personnalisée.</span><span class="sxs-lookup"><span data-stu-id="0b5e3-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

