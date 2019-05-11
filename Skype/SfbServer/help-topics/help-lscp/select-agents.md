---
title: Sélection des agents
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: Les agents sont les utilisateurs désignés pour répondre aux appels Response Group. Les groupes de réponse doivent disposer d’un groupe d’agents attribué, qui identifie les agents pouvant recevoir des appels pour le groupe de réponse. Pour créer un groupe d’agents, définissez un groupe personnalisé en sélectionnant des utilisateurs éligibles. Utilisateurs sont activés pour Skype pour Business Server et Enterprise Voice.
ms.openlocfilehash: f3e820287a998df827eb751c209ea69d292a4c0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924254"
---
# <a name="select-agents"></a><span data-ttu-id="1093e-106">Sélection des agents</span><span class="sxs-lookup"><span data-stu-id="1093e-106">Select Agents</span></span>

<span data-ttu-id="1093e-107">Les agents sont les utilisateurs désignés pour répondre aux appels Response Group.</span><span class="sxs-lookup"><span data-stu-id="1093e-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="1093e-108">Les groupes de réponse doivent disposer d’un groupe d’agents attribué, qui identifie les agents pouvant recevoir des appels pour le groupe de réponse.</span><span class="sxs-lookup"><span data-stu-id="1093e-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="1093e-109">Pour créer un groupe d’agents, définissez un groupe personnalisé en sélectionnant des utilisateurs éligibles.</span><span class="sxs-lookup"><span data-stu-id="1093e-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="1093e-110">Utilisateurs sont activés pour Skype pour Business Server et Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1093e-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="1093e-111">Vous pouvez utiliser la boîte de dialogue **Sélectionner des agents** pour sélectionner les utilisateurs à ajouter à un groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="1093e-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1093e-112">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="1093e-112">UI Reference</span></span>

<span data-ttu-id="1093e-113">La liste ci-dessous décrit les contrôles figurant dans la boîte de dialogue **Sélectionner des agents**.</span><span class="sxs-lookup"><span data-stu-id="1093e-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="1093e-114">**Rechercher** Recherche le SIP adresse ou nom complet pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1093e-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="1093e-115">Entrez tout ou partie du nom ou adresse.</span><span class="sxs-lookup"><span data-stu-id="1093e-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="1093e-116">Renseignez la zone de recherche pour afficher tous les utilisateurs activés pour Skype pour Business Server et Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1093e-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="1093e-117">**Nombre maximal d’utilisateurs à afficher** Modifie le nombre de résultats renvoyés qui sont affichés.</span><span class="sxs-lookup"><span data-stu-id="1093e-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="1093e-118">Ce compteur permet de limiter la recherche, si vous prévoyez de résultats.</span><span class="sxs-lookup"><span data-stu-id="1093e-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="1093e-119">La liste ci-dessous décrit les champs figurant dans la boîte de dialogue **Sélectionner des agents**.</span><span class="sxs-lookup"><span data-stu-id="1093e-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="1093e-120">**Agent** Affiche les noms d’utilisateur retournés par la recherche.</span><span class="sxs-lookup"><span data-stu-id="1093e-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="1093e-121">**Adresse SIP** Affiche les adresses SIP renvoyés par la recherche.</span><span class="sxs-lookup"><span data-stu-id="1093e-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="1093e-122">**Téléphonie** Affiche la valeur du champ **téléphonie** définie pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1093e-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="1093e-123">**Activé** Affiche la valeur du champ **activé pour Lync Server** définie pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1093e-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="1093e-124">Pour plus d’informations sur l’utilisation des groupes d’agents, reportez-vous à la rubrique [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="1093e-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


