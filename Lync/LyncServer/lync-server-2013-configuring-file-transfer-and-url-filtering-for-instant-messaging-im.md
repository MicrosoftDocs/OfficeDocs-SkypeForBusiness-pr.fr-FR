---
title: Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b741418790c5faf11c566afb27a477a67beb71ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="bed91-102">Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed91-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bed91-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bed91-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bed91-104">Le filtre de message instantané intelligent permet de protéger votre déploiement Lync Server 2013 contre la propagation des formes les plus courantes de virus, avec une dégradation minimale de l’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bed91-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="bed91-105">Utilisez le Filtre de message instantané intelligent pour configurer les filtres de façon à bloquer les messages instantanés non sollicités ou potentiellement dangereux en provenance de systèmes d’extrémité inconnus externes au pare-feu d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="bed91-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="bed91-106">Lors de la configuration des filtres, vous devez spécifier les critères à utiliser pour déterminer les éléments qui doivent être bloqués, tels que les messages instantanés contenant des liens hypertexte et des fichiers avec des préfixes et des extensions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="bed91-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="bed91-107">Cet outil comporte les filtrages suivants :</span><span class="sxs-lookup"><span data-stu-id="bed91-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="bed91-108">Filtrage d’URL amélioré</span><span class="sxs-lookup"><span data-stu-id="bed91-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="bed91-109">Filtrage du transfert de fichiers amélioré</span><span class="sxs-lookup"><span data-stu-id="bed91-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="bed91-110">La configuration de l’outil comporte les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="bed91-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="bed91-111">Configuration du filtrage d’URL</span><span class="sxs-lookup"><span data-stu-id="bed91-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="bed91-112">Configuration du filtrage de transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="bed91-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="bed91-113">Application des options de filtrage aux messages instantanés</span><span class="sxs-lookup"><span data-stu-id="bed91-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="bed91-114">Avant de déployer l’outil de filtrage de message instantané intelligent, vous devez comprendre comment les options de filtrage sont appliquées lorsque les messages sont routés d’un serveur Lync Server 2013 à un autre.</span><span class="sxs-lookup"><span data-stu-id="bed91-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="bed91-115">L’application de ces options de filtrage s’effectue toujours de la même manière, que les serveurs soient situés à l’intérieur d’une même organisation ou qu’ils soient disséminés dans plusieurs organisations.</span><span class="sxs-lookup"><span data-stu-id="bed91-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="bed91-116">Cette cohérence s’applique à la façon dont les messages personnalisés et les avertissements sont insérés dans les messages et transmis aux serveurs.</span><span class="sxs-lookup"><span data-stu-id="bed91-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="bed91-117">Le filtre de message instantané intelligent augmente les besoins en ressources processeur nécessaires au traitement des URL contenues dans un message.</span><span class="sxs-lookup"><span data-stu-id="bed91-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="bed91-118">Cette augmentation de la demande d’UC affecte également les performances de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bed91-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="bed91-119">À l’aide de la page de **filtrage d’URL** du groupe **messagerie instantanée et présence** dans le panneau de configuration Lync Server, vous pouvez bloquer une partie ou la totalité des liens hypertexte ou configurer un avertissement.</span><span class="sxs-lookup"><span data-stu-id="bed91-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="bed91-120">L’avertissement est inséré au début d’un message instantané qui contient un lien hypertexte lorsque vous choisissez l’option **Envoyer un message d’avertissement** pour **Préfixe de lien hypertexte** .</span><span class="sxs-lookup"><span data-stu-id="bed91-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="bed91-121">Lorsqu’un message instantané transite d’un serveur à un autre, les règles générales suivantes s’appliquent :</span><span class="sxs-lookup"><span data-stu-id="bed91-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="bed91-p105">Si un serveur bloque un message instantané (car vous avez activé la case à cocher **Bloquer les URL avec une extension de fichier** dans la page **Filtre d’URL** ou avez choisi l’option **Bloquer les liens hypertexte** pour **Préfixe de lien hypertexte**), un message d’erreur est retourné au client. Les serveurs suivants ne reçoivent pas ce message instantané.</span><span class="sxs-lookup"><span data-stu-id="bed91-p105">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client. Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="bed91-p106">Si un serveur (Serveur1) ajoute un avertissement à un message instantané qui contient un lien hypertexte actif, un autre serveur (Serveur2) qui reçoit ce message instantané peut décider, en fonction du lien hypertexte présent dans le message instantané, de bloquer ce dernier ou d’y ajouter un avertissement. Si Serveur2 est configuré de manière à uniquement ajouter un avertissement pour cette URL, l’avertissement ajouté précédemment par Serveur1 est supprimé, et l’avertissement configuré sur Serveur2 est ajouté au début du message instantané.</span><span class="sxs-lookup"><span data-stu-id="bed91-p106">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning. If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="bed91-126">Si vous exécutez Lync Server 2013 dans un environnement mixte, Live Communications Server 2005 avec SP1 est la version minimale requise pour utiliser l’application de filtre de message instantané intelligent.</span><span class="sxs-lookup"><span data-stu-id="bed91-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="bed91-127">Le Filtre de message instantané intelligent n’est pas pris en charge sur Live Communications Server 2005 sans SP1.</span><span class="sxs-lookup"><span data-stu-id="bed91-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="bed91-128">Filtrage d’URL</span><span class="sxs-lookup"><span data-stu-id="bed91-128">URL Filtering</span></span>

<span data-ttu-id="bed91-p108">Les URL sont filtrées à partir de leur préfixe de lien hypertexte. Voici quelques exemples de préfixes valides :</span><span class="sxs-lookup"><span data-stu-id="bed91-p108">URLs are filtered according to their hyperlink prefix. The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="bed91-131">www\*.</span><span class="sxs-lookup"><span data-stu-id="bed91-131">www\*.</span></span>

  - <span data-ttu-id="bed91-132">serveurFTP.</span><span class="sxs-lookup"><span data-stu-id="bed91-132">ftp.</span></span>

  - <span data-ttu-id="bed91-133">http</span><span class="sxs-lookup"><span data-stu-id="bed91-133">http:</span></span>

<span data-ttu-id="bed91-p109">Si vous ne configurez pas le filtre de message instantané de sorte qu’il filtre les URL, toutes les URL contenues dans des messages instantanés sont transmises sans modification via le serveur. Si vous configurez le filtre de message instantané de sorte qu’il filtre les URL, les URL dans les messages instantanés sont filtrées en tenant compte des options que vous sélectionnez dans la boîte de dialogue **Modifier le filtre d’URL** ou **Nouveau filtre d’URL**.</span><span class="sxs-lookup"><span data-stu-id="bed91-p109">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server. If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="bed91-136">**Activer le filtre**   d’URL cette option active le filtrage d’URL pour le déploiement global ou pour le site que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="bed91-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="bed91-137">**Bloquer les URL avec l’extension**   de fichier le filtre de message instantané bloque toute URL Internet ou Internet active qui contient un fichier dont l’extension est indiquée sous **extensions de types de fichiers à bloquer** dans la boîte de dialogue **modifier le filtre de fichier** .</span><span class="sxs-lookup"><span data-stu-id="bed91-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="bed91-138">Lorsqu’une URL est bloquée, l’expéditeur obtient un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="bed91-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="bed91-139">Lorsqu’elle est activée, cette option prévaut sur toutes les autres options de filtrage pour les extensions de fichier définies sous **Extensions de types de fichiers à bloquer**.</span><span class="sxs-lookup"><span data-stu-id="bed91-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="bed91-140">Le filtrage des extensions de fichier se limite aux noms de fichier standard.</span><span class="sxs-lookup"><span data-stu-id="bed91-140">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="bed91-141">Il se peut que le filtrage ne fonctionne pas en cas d’extensions de fichier imbriquées dans d’autres noms.</span><span class="sxs-lookup"><span data-stu-id="bed91-141">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="bed91-142">Pour configurer le traitement des liens hypertexte dans les conversations par messagerie instantanée, sélectionnez une des options suivantes sous **Préfixe de lien hypertexte** :</span><span class="sxs-lookup"><span data-stu-id="bed91-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="bed91-143">**Ne pas filtrer**   les URL dans les messages sont envoyées par le biais du serveur.</span><span class="sxs-lookup"><span data-stu-id="bed91-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="bed91-144">Lorsque vous choisissez cette option, la zone **Autoriser le message** apparaît.</span><span class="sxs-lookup"><span data-stu-id="bed91-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="bed91-145">Dans la zone **Autoriser le message**, indiquez l’avis que vous souhaitez insérer au début de chaque message instantané contenant des liens hypertexte.</span><span class="sxs-lookup"><span data-stu-id="bed91-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="bed91-146">Cet avis peut comporter jusqu’à 65 535 caractères.</span><span class="sxs-lookup"><span data-stu-id="bed91-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="bed91-147">**Bloquer les liens hypertexte**   la remise de messages instantanés contenant des liens hypertexte actifs est bloquée par Lync Server et un message d’erreur s’affiche pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="bed91-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="bed91-148">**Envoyer un message**   d’avertissement Lync Server autorise les liens hypertexte actifs dans les messages instantanés, mais il comprend un avertissement.</span><span class="sxs-lookup"><span data-stu-id="bed91-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="bed91-149">Lorsque vous choisissez cette option, la zone **Message d’avertissement** apparaît.</span><span class="sxs-lookup"><span data-stu-id="bed91-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="bed91-150">Dans la zone **Message d’avertissement**, tapez l’avertissement que vous voulez inclure aux messages instantanés contenant des liens hypertexte valides.</span><span class="sxs-lookup"><span data-stu-id="bed91-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="bed91-151">Par exemple, cet avertissement peut indiquer les dangers potentiels qu’encourt l’utilisateur s’il clique sur un lien inconnu ou il peut rappeler les stratégies et les conditions pertinentes de votre organisation concernant l’utilisation des liens.</span><span class="sxs-lookup"><span data-stu-id="bed91-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="bed91-152">L’avertissement peut comporter jusqu’à 65 535  caractères.</span><span class="sxs-lookup"><span data-stu-id="bed91-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="bed91-153">Si vous sélectionnez **Bloquer les liens hypertexte** ou **Envoyer un message d’avertissement**, les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="bed91-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="bed91-154">**Exclure les liens hypertexte de l’intranet local**   le filtre de messages instantanés bloque uniquement les URL Internet.</span><span class="sxs-lookup"><span data-stu-id="bed91-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="bed91-155">Les URL correspondant à des emplacements dans votre intranet sont transmises sans modification via le serveur.</span><span class="sxs-lookup"><span data-stu-id="bed91-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="bed91-156">Toutefois, les URL intranet auxquelles les serveurs individuels exécutant Lync Server sont passés dépendent des types de sites Web locaux considérés comme faisant partie de leur zone intranet.</span><span class="sxs-lookup"><span data-stu-id="bed91-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="bed91-157">Pour vérifier les paramètres de la zone intranet d’un serveur, reportez-vous à la procédure « pour configurer vos paramètres intranet dans Internet Explorer » dans [modifier le filtre d’URL par défaut dans Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).</span><span class="sxs-lookup"><span data-stu-id="bed91-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="bed91-158">**Filtrez ces**   préfixes de liens hypertexte pour choisir les préfixes à bloquer, cliquez sur **Sélectionner**, puis, dans sélectionner un préfixe de **lien hypertexte**, ajoutez les préfixes à la liste préfixes de **liens hypertexte** .</span><span class="sxs-lookup"><span data-stu-id="bed91-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="bed91-159">Tous les préfixes sauf **href** doivent se terminer par un point ou un point-virgule, ou un astérisque suivi d’un point.</span><span class="sxs-lookup"><span data-stu-id="bed91-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="bed91-160">Les préfixes valides peuvent contenir n’importe quel caractère dans le jeu de caractères d'\*URL valides à l’exception de l’astérisque ().</span><span class="sxs-lookup"><span data-stu-id="bed91-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="bed91-161">Le jeu de caractères d’URL valides \# \*est : +/0123456789 =\_ \` @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ abcdefghijklmnopqrstuvwxyz | ~</span><span class="sxs-lookup"><span data-stu-id="bed91-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="bed91-162">Filtrage de transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="bed91-162">File Transfer Filtering</span></span>

<span data-ttu-id="bed91-p116">Le filtrage de transfert de fichiers concerne les messages instantanés et les conférences. Pour les conférences, ces paramètres concernent la fonctionnalité des documents dans le client Office Live Meeting 2007 et les fonctionnalités de lecture multimédia.</span><span class="sxs-lookup"><span data-stu-id="bed91-p116">Filter transfer filtering affects both instant messages and conferences. For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="bed91-165">Lync Server offre également des options de paramètres de transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bed91-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="bed91-166">Cette option côté serveur est proposée en plus des contrôles côté client disponibles dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bed91-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="bed91-p118">Vous pouvez filtrer les transferts de fichiers au cours des conversations par messagerie instantanée lorsque vous utilisez la fonctionnalité des documents dans le client Office Live Meeting 2007 et les fonctionnalités de lecture multimédia pour tous les types de fichiers. Vous pouvez définir les options suivantes pour contrôler les transferts de fichiers :</span><span class="sxs-lookup"><span data-stu-id="bed91-p118">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types. You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="bed91-169">**Activer le filtre**   de fichiers cette option active le filtrage de fichiers pour le déploiement global ou pour le site que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="bed91-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="bed91-170">Lorsque vous activez le filtre de fichiers, vous pouvez choisir l’une des options suivantes dans **Transfert de fichiers** :</span><span class="sxs-lookup"><span data-stu-id="bed91-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="bed91-171">**Bloquer des types**   de fichiers spécifiques vous spécifiez les demandes de transfert de fichiers filtrées par le serveur en spécifiant une liste d’extensions de fichiers à bloquer.</span><span class="sxs-lookup"><span data-stu-id="bed91-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="bed91-172">Les entrées de la liste peuvent contenir tous les caractères standard, mais pas le caractère\*générique ().</span><span class="sxs-lookup"><span data-stu-id="bed91-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="bed91-173">Dans le client Office Live Meeting 2007, la fonctionnalité des documents est activée, mais les fichiers avec cette extension ne peuvent pas être téléchargés.</span><span class="sxs-lookup"><span data-stu-id="bed91-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="bed91-174">Si vous activez la case à cocher **Bloquer les URL avec une extension de fichier** dans les paramètres d’un filtre d’URL répertorié sous l’onglet **Filtre d’URL**, le filtre d’URL utilise cette même liste pour bloquer les liens hypertexte actifs qui contiennent ces extensions de fichier.</span><span class="sxs-lookup"><span data-stu-id="bed91-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="bed91-175">Pour choisir les types de fichiers que vous souhaitez bloquer, cliquez sur **Sélectionner**, puis dans **Sélectionner un type de fichier**, ajoutez les extensions de type de fichier à la liste **Extensions de types de fichiers sélectionnées**.</span><span class="sxs-lookup"><span data-stu-id="bed91-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="bed91-176">**Bloquer tout**   le serveur supprime tous les messages instantanés qui contiennent des demandes de transfert de fichiers et renvoie un message d’erreur à l’expéditeur de la demande.</span><span class="sxs-lookup"><span data-stu-id="bed91-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="bed91-177">La fonctionnalité des documents est désactivée dans le client Office Live Meeting 2007.</span><span class="sxs-lookup"><span data-stu-id="bed91-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="bed91-p121">Le filtrage des extensions de fichier se limite aux noms de fichier standard. Il se peut que le filtrage ne fonctionne pas en cas d’extensions de fichier imbriquées dans d’autres noms.</span><span class="sxs-lookup"><span data-stu-id="bed91-p121">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bed91-180">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="bed91-180">In This Section</span></span>

  - [<span data-ttu-id="bed91-181">Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed91-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="bed91-182">Créer un nouveau filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique</span><span class="sxs-lookup"><span data-stu-id="bed91-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="bed91-183">Modifier le filtre d’URL par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed91-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="bed91-184">Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="bed91-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bed91-185">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bed91-185">See Also</span></span>


[<span data-ttu-id="bed91-186">Gestion des paramètres de messagerie instantanée et de présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed91-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

