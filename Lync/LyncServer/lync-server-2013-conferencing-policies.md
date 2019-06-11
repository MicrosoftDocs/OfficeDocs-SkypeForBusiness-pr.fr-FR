---
title: 'Lync Server 2013: stratégies de conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing policies
ms:assetid: 8f92eb7c-ee66-4df6-a726-4bff93b122cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688133(v=OCS.15)
ms:contentKeyID: 49733732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b60b521c69b821dacfe8bd569a6300b4c21e0287
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="c6cbe-102">Stratégies de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6cbe-102">Conferencing policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6cbe-103">_**Dernière modification de la rubrique:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="c6cbe-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="c6cbe-104">La stratégie de conférence définit les fonctionnalités que les utilisateurs peuvent utiliser pendant une conférence (également appelée réunion).</span><span class="sxs-lookup"><span data-stu-id="c6cbe-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span> <span data-ttu-id="c6cbe-105">Les paramètres d’une stratégie de conférence englobent une grande variété d’options de planification et de participation, notamment la possibilité d’utiliser des fonctions audio et vidéo IP dans une réunion et de déterminer le nombre maximal de participants.</span><span class="sxs-lookup"><span data-stu-id="c6cbe-105">Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="c6cbe-106">Les administrateurs peuvent utiliser une stratégie de conférence pour gérer la sécurité, la bande passante et les aspects juridiques des réunions.</span><span class="sxs-lookup"><span data-stu-id="c6cbe-106">Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="c6cbe-107">Vous pouvez définir une stratégie de conférence sur trois niveaux : étendue globale, étendue de site et étendue d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6cbe-107">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="c6cbe-108">Les paramètres s’appliquent à un utilisateur spécifique de l’étendue la plus étroite à la plus large.</span><span class="sxs-lookup"><span data-stu-id="c6cbe-108">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="c6cbe-109">Si vous attribuez une stratégie utilisateur à un utilisateur, ces paramètres sont prioritaires.</span><span class="sxs-lookup"><span data-stu-id="c6cbe-109">If you assign a user policy to a user, those settings take precedence.</span></span> <span data-ttu-id="c6cbe-110">Si vous n’affectez pas une stratégie utilisateur à un utilisateur, les paramètres de la stratégie par site s’appliquent.</span><span class="sxs-lookup"><span data-stu-id="c6cbe-110">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="c6cbe-111">Si vous n’appliquez aucune stratégie par utilisateur ou par site, la stratégie globale fournit les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="c6cbe-111">If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="c6cbe-112">Une stratégie globale existe par défaut, par conséquent vous ne pouvez pas en créer une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="c6cbe-112">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="c6cbe-113">Vous ne pouvez pas non plus supprimer la stratégie globale existante, mais vous pouvez modifier la stratégie globale existante pour personnaliser les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="c6cbe-113">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c6cbe-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c6cbe-114">In This Section</span></span>

  - [<span data-ttu-id="c6cbe-115">Afficher les informations de stratégie de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6cbe-115">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="c6cbe-116">Création ou modification d’une stratégie de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6cbe-116">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="c6cbe-117">Supprimer une stratégie de conférence existante dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6cbe-117">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="c6cbe-118">Référence des paramètres de stratégie de conférence pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6cbe-118">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

