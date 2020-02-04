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
ms.openlocfilehash: e6c5a6053118b14b68c49a7fdaa6f444aca7ad23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="129ec-102">Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="129ec-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="129ec-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="129ec-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="129ec-104">L’outil de filtrage de messages instantanés intelligents vous aide à protéger votre déploiement de Lync Server 2013 contre la répartition des formes les plus fréquemment utilisées avec une dégradation minimale de l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="129ec-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="129ec-105">Utilisez le filtre de message instantané intelligent pour configurer des filtres permettant de bloquer les messages instantanés non sollicités ou potentiellement dangereux de points de terminaison inconnus en dehors du pare-feu de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="129ec-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="129ec-106">Vous pouvez configurer des filtres en spécifiant les critères à utiliser pour déterminer ce qui devrait être bloqué (par exemple, les messages instantanés contenant des liens hypertexte avec des préfixes spécifiques et des fichiers avec des extensions spécifiques).</span><span class="sxs-lookup"><span data-stu-id="129ec-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="129ec-107">Le filtre de message instantané intelligent fournit les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="129ec-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="129ec-108">Amélioration du filtrage d’URL.</span><span class="sxs-lookup"><span data-stu-id="129ec-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="129ec-109">Amélioration du filtrage du transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="129ec-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="129ec-110">La configuration du filtre de message instantané intelligent inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="129ec-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="129ec-111">Configuration du filtrage d’URL.</span><span class="sxs-lookup"><span data-stu-id="129ec-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="129ec-112">Configuration du filtrage de transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="129ec-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="129ec-113">Application des options de filtre aux messages instantanés</span><span class="sxs-lookup"><span data-stu-id="129ec-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="129ec-114">Avant de déployer l’outil de filtre de messages INSTANTANÉs intelligents, vous devez comprendre comment les options de filtre sont appliquées lorsque les messages sont routés d’un serveur Lync Server 2013 vers un autre.</span><span class="sxs-lookup"><span data-stu-id="129ec-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="129ec-115">La façon dont ces options de filtrage sont appliquées est cohérente, qu’il s’agisse de serveurs au sein d’une organisation unique ou de limites de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="129ec-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="129ec-116">Cette cohérence s’applique au mode d’insertion des avis personnalisés et des textes d’avertissement dans les messages et envoyés sur plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="129ec-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="129ec-117">Le filtre de message instantané augmente le volume de ressources processeur requises pour traiter les URL d’un message.</span><span class="sxs-lookup"><span data-stu-id="129ec-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="129ec-118">Cette augmentation de la demande de l’UC affecte également les performances de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="129ec-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="129ec-119">À l’aide de la page de **filtre d’URL** du groupe **messagerie instantanée et présence** dans le panneau de configuration de Lync Server, vous pouvez bloquer tout ou partie des liens hypertexte ou configurer un avertissement.</span><span class="sxs-lookup"><span data-stu-id="129ec-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="129ec-120">Le message d’avertissement est inséré au début d’un message instantané contenant un lien hypertexte lorsque vous sélectionnez l’option **lien hypertexte : préfixe** de l’option **Envoyer un message d’avertissement**.</span><span class="sxs-lookup"><span data-stu-id="129ec-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="129ec-121">Lorsqu’un message instantané est acheminé d’un serveur à un autre, les instructions générales suivantes s’appliquent :</span><span class="sxs-lookup"><span data-stu-id="129ec-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="129ec-122">Si un serveur bloque un message instantané (dans la mesure où vous avez activé la case à cocher **bloquer les URL avec l’extension de fichier** sur la page de filtre d' **URL** ou que vous avez choisi l’option **préfixe du lien hypertexte** **),** un message d’erreur est retourné au client.</span><span class="sxs-lookup"><span data-stu-id="129ec-122">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client.</span></span> <span data-ttu-id="129ec-123">Les serveurs suivants ne reçoivent pas ce message instantané.</span><span class="sxs-lookup"><span data-stu-id="129ec-123">Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="129ec-124">Si un serveur (serveur1) ajoute un avertissement à un message instantané contenant un lien hypertexte actif, un serveur ultérieur (server2) qui reçoit ce message instantané peut toujours effectuer une autre action en fonction de cet hyperlien actif présent dans le message instantané et bloquer le Envoyer un message instantané ou ajouter un avertissement.</span><span class="sxs-lookup"><span data-stu-id="129ec-124">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning.</span></span> <span data-ttu-id="129ec-125">Si Server2 est configuré uniquement pour ajouter un avertissement pour cette URL, l’avertissement précédent ajouté par Server1 est supprimé et l’avertissement configuré sur Server2 est ajouté au début du message instantané.</span><span class="sxs-lookup"><span data-stu-id="129ec-125">If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="129ec-126">Si vous exécutez Lync Server 2013 dans un environnement mixte, Live Communications Server 2005 avec SP1 est la version minimale requise pour utiliser l’application de filtre de message instantané intelligent.</span><span class="sxs-lookup"><span data-stu-id="129ec-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="129ec-127">Le filtre de messagerie instantanée intelligent n’est pas pris en charge sur Live Communications Server 2005 sans SP1.</span><span class="sxs-lookup"><span data-stu-id="129ec-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="129ec-128">Filtrage d’URL</span><span class="sxs-lookup"><span data-stu-id="129ec-128">URL Filtering</span></span>

<span data-ttu-id="129ec-129">Les URL sont filtrées en fonction de leur préfixe de lien hypertexte.</span><span class="sxs-lookup"><span data-stu-id="129ec-129">URLs are filtered according to their hyperlink prefix.</span></span> <span data-ttu-id="129ec-130">Les exemples suivants sont des préfixes valides :</span><span class="sxs-lookup"><span data-stu-id="129ec-130">The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="129ec-131">www\*.</span><span class="sxs-lookup"><span data-stu-id="129ec-131">www\*.</span></span>

  - <span data-ttu-id="129ec-132">FTP.</span><span class="sxs-lookup"><span data-stu-id="129ec-132">ftp.</span></span>

  - <span data-ttu-id="129ec-133">http</span><span class="sxs-lookup"><span data-stu-id="129ec-133">http:</span></span>

<span data-ttu-id="129ec-134">Si vous ne configurez pas le filtre des messages instantanés pour effectuer un filtrage d’URL, toutes les URL contenues dans les messages instantanés ne sont pas modifiées par le biais du serveur.</span><span class="sxs-lookup"><span data-stu-id="129ec-134">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server.</span></span> <span data-ttu-id="129ec-135">Si vous configurez le filtre des messages instantanés pour effectuer le filtrage d’URL, les URL dans les messages instantanés sont filtrées conformément aux options que vous avez sélectionnées dans la boîte de dialogue **modifier le filtre d’URL** ou **nouveau filtre d’URL** .</span><span class="sxs-lookup"><span data-stu-id="129ec-135">If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="129ec-136">**Activer le filtre**   d’URL cette option active le filtrage d’URL pour le déploiement global ou pour le site que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="129ec-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="129ec-137">**Bloquer les URL avec l’extension**   de fichier le filtre de message instantané bloque toutes les URL Internet ou intranet actives qui contiennent un fichier doté d’une extension répertoriées sous **extensions de type de fichier à bloquer** dans la boîte de dialogue **modifier le filtre de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="129ec-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="129ec-138">Lorsqu’une URL est bloquée, un message d’erreur s’affiche à l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="129ec-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="129ec-139">Lorsque cette option est sélectionnée, elle est prioritaire sur toutes les autres options de filtrage pour les extensions de fichiers définies sous **extensions de type de fichier à bloquer**.</span><span class="sxs-lookup"><span data-stu-id="129ec-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="129ec-140">Le filtrage d’extensions de fichier est limité aux noms de fichiers standard.</span><span class="sxs-lookup"><span data-stu-id="129ec-140">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="129ec-141">Il est possible que le filtrage ne fonctionne pas avec les extensions de fichier imbriquées dans d’autres noms.</span><span class="sxs-lookup"><span data-stu-id="129ec-141">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="129ec-142">Pour configurer la gestion des liens hypertexte dans les conversations par messagerie instantanée, sélectionnez l’une des options suivantes sous **préfixe du lien hypertexte**:</span><span class="sxs-lookup"><span data-stu-id="129ec-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="129ec-143">**Ne filtrez**   pas les URL des messages envoyés par le biais du serveur.</span><span class="sxs-lookup"><span data-stu-id="129ec-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="129ec-144">Lorsque vous choisissez cette option, la boîte de **dialogue autoriser le message** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="129ec-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="129ec-145">Dans la boîte de dialogue **autoriser le message** , spécifiez l’avis que vous voulez insérer au début de chaque message instantané contenant des liens hypertexte.</span><span class="sxs-lookup"><span data-stu-id="129ec-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="129ec-146">Ce message ne peut pas contenir plus de 65535 caractères.</span><span class="sxs-lookup"><span data-stu-id="129ec-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="129ec-147">**Bloquer**   la remise de liens hypertexte pour les messages instantanés contenant des liens hypertexte actifs est bloqué par Lync Server et un message d’erreur s’affiche à l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="129ec-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="129ec-148">**Envoyer un message**   d’avertissement Lync Server autorise les liens hypertexte actifs dans les messages instantanés, mais il inclut un avertissement.</span><span class="sxs-lookup"><span data-stu-id="129ec-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="129ec-149">Lorsque vous choisissez cette option, la boîte de **dialogue Avertissement** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="129ec-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="129ec-150">Dans la boîte de **dialogue message d’avertissement** , vous devez taper l’avertissement que vous voulez inclure dans les messages instantanés contenant des liens hypertexte valides.</span><span class="sxs-lookup"><span data-stu-id="129ec-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="129ec-151">Par exemple, ce message d’avertissement peut faire référence aux dangers potentiels d’un clic sur un lien inconnu, ou faire référence aux politiques et exigences pertinentes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="129ec-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="129ec-152">Le message d’avertissement ne peut pas contenir plus de 65535 caractères.</span><span class="sxs-lookup"><span data-stu-id="129ec-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="129ec-153">Si vous sélectionnez **bloquer les liens hypertexte** ou **Envoyer un message d’avertissement**, les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="129ec-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="129ec-154">**Exclure les liens hypertexte de l’intranet local**   le filtre de message instantané bloque uniquement les URL Internet.</span><span class="sxs-lookup"><span data-stu-id="129ec-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="129ec-155">Les URL des emplacements au sein de votre intranet sont transmises sans modification sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="129ec-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="129ec-156">Toutefois, les URL de l’intranet qui sont prises en charge par les serveurs exécutant Lync Server en fonction des types de sites Web locaux qui sont considérés comme faisant partie de leur zone intranet.</span><span class="sxs-lookup"><span data-stu-id="129ec-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="129ec-157">Pour vérifier les paramètres de zone intranet d’un serveur, reportez-vous à la procédure « pour configurer vos paramètres intranet dans Internet Explorer » dans [modifier le filtre d’URL par défaut dans Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).</span><span class="sxs-lookup"><span data-stu-id="129ec-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="129ec-158">**Filtrer ces préfixes**   pour sélectionner les préfixes que vous voulez bloquer, cliquez sur **Sélectionner**, puis, dans **Sélectionner un préfixe de lien hypertexte**, ajoutez les préfixes à la liste préfixes du **lien hypertexte** .</span><span class="sxs-lookup"><span data-stu-id="129ec-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="129ec-159">Tous les préfixes sauf **href** doivent se terminer par un point ou une virgule, ou un astérisque suivi par un point.</span><span class="sxs-lookup"><span data-stu-id="129ec-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="129ec-160">Les préfixes valides peuvent contenir des caractères dans l’ensemble de caractères d’URL valides sauf l’astérisque (\*).</span><span class="sxs-lookup"><span data-stu-id="129ec-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="129ec-161">Le jeu de caractères d’URL valides \# \*est : +/0123456789 =\_ \` @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ abcdefghijklmnopqrstuvwxyz | ~</span><span class="sxs-lookup"><span data-stu-id="129ec-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="129ec-162">Filtrage du transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="129ec-162">File Transfer Filtering</span></span>

<span data-ttu-id="129ec-163">Le filtrage de transfert de filtre affecte les messages instantanés et les conférences.</span><span class="sxs-lookup"><span data-stu-id="129ec-163">Filter transfer filtering affects both instant messages and conferences.</span></span> <span data-ttu-id="129ec-164">En ce qui concerne les conférences, ces paramètres affectent la fonctionnalité documents du client Office Live Meeting 2007 et des fonctionnalités de lecture multimédia.</span><span class="sxs-lookup"><span data-stu-id="129ec-164">For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="129ec-165">Lync Server propose également des options de paramètres de transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="129ec-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="129ec-166">Cette option côté serveur est proposée en plus des contrôles côté client disponibles dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="129ec-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="129ec-167">Vous pouvez filtrer les transferts de fichiers lors des conversations par messagerie instantanée, lorsque vous utilisez la fonctionnalité documents du client 2007 Office Live Meeting et des fonctionnalités de lecture multimédias pour tous les types de fichiers.</span><span class="sxs-lookup"><span data-stu-id="129ec-167">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types.</span></span> <span data-ttu-id="129ec-168">Vous pouvez définir les options suivantes pour contrôler les transferts de fichiers :</span><span class="sxs-lookup"><span data-stu-id="129ec-168">You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="129ec-169">**Activer le filtre**   de fichiers cette option active le filtrage de fichiers pour le déploiement global ou pour le site que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="129ec-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="129ec-170">Lorsque vous activez le filtre de fichier, vous pouvez choisir l’une des options suivantes dans **transfert de fichier**:</span><span class="sxs-lookup"><span data-stu-id="129ec-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="129ec-171">**Bloquer des types**   de fichiers spécifiques vous spécifiez les demandes de transfert de fichiers filtrées par le serveur en spécifiant une liste d’extensions de fichier à bloquer.</span><span class="sxs-lookup"><span data-stu-id="129ec-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="129ec-172">Les entrées de la liste peuvent contenir tous les caractères standard, à l’exception du\*caractère générique ().</span><span class="sxs-lookup"><span data-stu-id="129ec-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="129ec-173">Dans le client Office Live Meeting 2007, la fonctionnalité documents est activée alors qu’il n’est pas possible de télécharger ou de télécharger un fichier avec cette extension.</span><span class="sxs-lookup"><span data-stu-id="129ec-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="129ec-174">Si vous activez la case à cocher **bloquer les URL avec l’extension de fichier** dans les paramètres d’un filtre d’URL indiqué dans l’onglet filtre d' **URL** , le filtre d’URL utilise la même liste pour bloquer les liens hypertexte actifs qui contiennent l’une de ces extensions de fichier.</span><span class="sxs-lookup"><span data-stu-id="129ec-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="129ec-175">Pour choisir les types de fichiers que vous souhaitez bloquer, cliquez sur **Sélectionner**, puis, sous **type de fichier**, ajoutez les extensions de type de fichier à la liste extensions de type de fichier **sélectionnées** .</span><span class="sxs-lookup"><span data-stu-id="129ec-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="129ec-176">**Bloquer tout**   le serveur supprime tous les messages instantanés qui contiennent des demandes de transfert de fichiers et renvoie un message d’erreur à l’expéditeur de la requête.</span><span class="sxs-lookup"><span data-stu-id="129ec-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="129ec-177">La fonctionnalité documents du client 2007 Office Live Meeting est désactivée.</span><span class="sxs-lookup"><span data-stu-id="129ec-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="129ec-178">Le filtrage d’extensions de fichier est limité aux noms de fichiers standard.</span><span class="sxs-lookup"><span data-stu-id="129ec-178">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="129ec-179">Il est possible que le filtrage ne fonctionne pas avec les extensions de fichier imbriquées dans d’autres noms.</span><span class="sxs-lookup"><span data-stu-id="129ec-179">Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="129ec-180">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="129ec-180">In This Section</span></span>

  - [<span data-ttu-id="129ec-181">Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="129ec-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="129ec-182">Créer un filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique</span><span class="sxs-lookup"><span data-stu-id="129ec-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="129ec-183">Modifier le filtre d’URL par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="129ec-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="129ec-184">Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="129ec-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="129ec-185">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="129ec-185">See Also</span></span>


[<span data-ttu-id="129ec-186">Gestion des paramètres de messagerie instantanée et de présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="129ec-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

