---
title: 'Lync Server 2013 : réduction des messages instantanés non sollicités'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5042c4400cdf16be650a3c2c74ed756f01d93114
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="47604-102">Réduction des messages instantanés non sollicités pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47604-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47604-103">_**Dernière modification de la rubrique:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="47604-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="47604-104">L’application de filtre de messages instantanés intelligents vous aide à protéger votre déploiement de Microsoft Lync Server 2013 contre les virus les plus fréquents avec une dégradation minimale de l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="47604-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="47604-105">Ce filtre fournit les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="47604-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="47604-106">Amélioration du filtrage d’URL</span><span class="sxs-lookup"><span data-stu-id="47604-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="47604-107">Amélioration du filtrage du transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="47604-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="47604-108">Utilisez le filtre de message instantané intelligent pour configurer des filtres permettant de bloquer les messages instantanés non sollicités ou potentiellement dangereux de points de terminaison inconnus en dehors du pare-feu de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="47604-108">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="47604-109">Vous pouvez configurer des filtres en spécifiant les critères à utiliser pour déterminer ce qui devrait être bloqué (par exemple, les messages instantanés contenant des liens hypertexte et des fichiers avec des extensions spécifiques).</span><span class="sxs-lookup"><span data-stu-id="47604-109">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="47604-110">Avant de déployer l’application de filtre de messages INSTANTANÉs intelligents, vous devez comprendre comment les options de filtre sont appliquées lorsque les messages sont routés d’un serveur Lync Server 2013 à un autre.</span><span class="sxs-lookup"><span data-stu-id="47604-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="47604-111">La façon dont ces options de filtrage sont appliquées est cohérente, qu’il s’agisse de serveurs au sein d’une organisation unique ou de limites de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="47604-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="47604-112">Cette cohérence s’applique au mode d’insertion des avis personnalisés et des textes d’avertissement dans les messages et envoyés sur plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="47604-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="47604-113">L’option de filtrage recommandée consiste à autoriser les messages instantanés avec des liens hypertexte, mais ils nécessitent le filtre de messagerie instantanée intelligent pour désactiver le lien en insérant un trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="47604-113">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="47604-114">Si vous choisissez cette option, vous avez la possibilité d’ajouter un avis aux utilisateurs qui s’affichent au début de chaque message instantané contenant un lien hypertexte.</span><span class="sxs-lookup"><span data-stu-id="47604-114">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="47604-115">Une deuxième option de filtrage consiste à autoriser les messages instantanés comportant des liens hypertexte non modifiés.</span><span class="sxs-lookup"><span data-stu-id="47604-115">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="47604-116">Si vous choisissez cette option, vous avez la possibilité d’utiliser l’option supplémentaire (recommandée) pour composer un avertissement aux utilisateurs insérés dans chaque message.</span><span class="sxs-lookup"><span data-stu-id="47604-116">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="47604-117">Une troisième option consiste à bloquer tous les messages instantanés qui contiennent des liens hypertexte.</span><span class="sxs-lookup"><span data-stu-id="47604-117">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="47604-118">Si vous choisissez cette option, le serveur envoie un message d’avertissement à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="47604-118">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="47604-119">Vous devez rédiger cet avertissement.</span><span class="sxs-lookup"><span data-stu-id="47604-119">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

