---
title: 'Lync Server 2013 : réduction des messages instantanés non sollicités'
description: 'Lync Server 2013 : réduction des messages instantanés non sollicités.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 294c53a6b82b4dc345fbb9afcf9983d5bd35893a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559110"
---
# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="8d216-103">Réduction des messages instantanés non sollicités pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d216-103">Reducing unsolicited IM for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d216-104">_**Dernière modification de la rubrique :** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="8d216-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="8d216-105">L’application de filtre de message instantané intelligent permet de protéger votre déploiement Microsoft Lync Server 2013 contre les virus les plus courants avec une dégradation minimale de l’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8d216-105">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="8d216-106">Le filtre de message instantané intelligent fournit les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="8d216-106">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="8d216-107">Filtrage d’URL amélioré</span><span class="sxs-lookup"><span data-stu-id="8d216-107">Enhanced URL filtering</span></span>

  - <span data-ttu-id="8d216-108">Filtrage amélioré de transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="8d216-108">Enhanced file transfer filtering</span></span>

<span data-ttu-id="8d216-109">Utilisez le Filtre de message instantané intelligent pour configurer les filtres de façon à bloquer les messages instantanés non sollicités ou potentiellement dangereux en provenance de systèmes d’extrémité inconnus externes au pare-feu d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="8d216-109">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="8d216-110">Vous configurez des filtres en spécifiant les critères à utiliser pour déterminer les éléments qui doivent être bloqués, tels que les messages instantanés contenant des liens hypertexte et des fichiers avec des extensions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="8d216-110">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="8d216-111">Avant de déployer l’application de filtre de message instantané intelligent, vous devez comprendre comment les options de filtrage sont appliquées lorsque les messages sont routés d’un serveur Lync Server 2013 à un autre.</span><span class="sxs-lookup"><span data-stu-id="8d216-111">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="8d216-112">L’application de ces options de filtrage s’effectue toujours de la même manière, que les serveurs soient situés à l’intérieur d’une même organisation ou qu’ils soient disséminés dans plusieurs organisations.</span><span class="sxs-lookup"><span data-stu-id="8d216-112">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="8d216-113">Cette cohérence s’applique à la façon dont l’avis personnalisé et les textes d’avertissement sont insérés dans les messages et envoyés sur plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="8d216-113">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="8d216-114">L’option de filtrage recommandé est d’autoriser les messages instantanés avec des liens hypertexte mais de demander au filtre de messagerie instantanée intelligent de désactiver le lien en insérant un trait de soulignement avant lui.</span><span class="sxs-lookup"><span data-stu-id="8d216-114">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="8d216-115">Si vous choisissez cette option, vous avez la possibilité supplémentaire de rédiger une notification aux utilisateurs qui apparaît au début de chaque message instantané contenant un lien hypertexte.</span><span class="sxs-lookup"><span data-stu-id="8d216-115">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="8d216-116">Une deuxième option de filtrage consiste à autoriser les messages instantanés avec des liens hypertexte non modifiés.</span><span class="sxs-lookup"><span data-stu-id="8d216-116">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="8d216-117">Si vous choisissez cette option, vous disposez de l’option supplémentaire (recommandé) pour rédiger un avertissement aux utilisateurs qui sont insérés dans chaque message.</span><span class="sxs-lookup"><span data-stu-id="8d216-117">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="8d216-118">Une troisième option consiste à bloquer tous les messages instantanés qui contiennent des liens hypertexte.</span><span class="sxs-lookup"><span data-stu-id="8d216-118">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="8d216-119">Si vous choisissez cette option, le serveur envoie un avertissement à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8d216-119">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="8d216-120">Vous devez rédiger cet avertissement.</span><span class="sxs-lookup"><span data-stu-id="8d216-120">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

