---
title: Sélection des agents
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: Les agents sont des utilisateurs désignés pour répondre aux appels de groupe de réponse. Les groupes de réponse doivent disposer d’un groupe d’agents attribué, qui identifie les agents pouvant recevoir des appels pour le groupe de réponse. Pour créer un groupe d’agents, définissez un groupe personnalisé en sélectionnant des utilisateurs éligibles. Les utilisateurs éligibles sont activés pour Skype entreprise Server et voix entreprise.
ms.openlocfilehash: 2950295bcf78ee2c7c904375d009a8fba085b85f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822307"
---
# <a name="select-agents"></a><span data-ttu-id="0db75-106">Sélection des agents</span><span class="sxs-lookup"><span data-stu-id="0db75-106">Select Agents</span></span>

<span data-ttu-id="0db75-107">Les agents sont des utilisateurs désignés pour répondre aux appels de groupe de réponse.</span><span class="sxs-lookup"><span data-stu-id="0db75-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="0db75-108">Les groupes de réponse doivent disposer d’un groupe d’agents attribué, qui identifie les agents pouvant recevoir des appels pour le groupe de réponse.</span><span class="sxs-lookup"><span data-stu-id="0db75-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="0db75-109">Pour créer un groupe d’agents, définissez un groupe personnalisé en sélectionnant des utilisateurs éligibles.</span><span class="sxs-lookup"><span data-stu-id="0db75-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="0db75-110">Les utilisateurs éligibles sont activés pour Skype entreprise Server et voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="0db75-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="0db75-111">Vous pouvez utiliser la boîte de dialogue **Sélectionner des agents** pour sélectionner les utilisateurs à ajouter à un groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="0db75-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0db75-112">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="0db75-112">UI Reference</span></span>

<span data-ttu-id="0db75-113">La liste ci-dessous décrit les contrôles figurant dans la boîte de dialogue **Sélectionner des agents**.</span><span class="sxs-lookup"><span data-stu-id="0db75-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="0db75-114">**Recherchez** Recherche l’adresse SIP ou le nom d’affichage d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0db75-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="0db75-115">Entrez tout ou partie de l’adresse ou du nom.</span><span class="sxs-lookup"><span data-stu-id="0db75-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="0db75-116">Laissez la zone de recherche vide pour afficher tous les utilisateurs qui sont activés pour Skype entreprise Server et voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="0db75-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="0db75-117">**Nombre maximal d’utilisateurs à afficher** Change le nombre de résultats retournés qui s’affichent.</span><span class="sxs-lookup"><span data-stu-id="0db75-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="0db75-118">Utilisez ce compteur pour limiter la recherche si vous prévoyez de nombreux résultats.</span><span class="sxs-lookup"><span data-stu-id="0db75-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="0db75-119">La liste ci-dessous décrit les champs figurant dans la boîte de dialogue **Sélectionner des agents**.</span><span class="sxs-lookup"><span data-stu-id="0db75-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="0db75-120">**Agent** Affiche le nom d’utilisateur retourné par la recherche.</span><span class="sxs-lookup"><span data-stu-id="0db75-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="0db75-121">**Adresse SIP** Affiche les adresses SIP de l’utilisateur renvoyées par la recherche.</span><span class="sxs-lookup"><span data-stu-id="0db75-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="0db75-122">**Téléphonie** Affiche la valeur du champ de **téléphonie** défini pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0db75-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="0db75-123">**Activée** Affiche la valeur du champ **activé pour Lync Server** défini pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0db75-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="0db75-124">Pour plus d’informations sur l’utilisation des groupes d’agents, reportez-vous à la rubrique [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="0db75-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


