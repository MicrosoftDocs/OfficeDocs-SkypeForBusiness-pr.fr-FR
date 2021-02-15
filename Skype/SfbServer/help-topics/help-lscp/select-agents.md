---
title: Sélection des agents
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Les agents sont des utilisateurs désignés pour répondre aux appels Response Group. Les groupes Response Group doivent avoir un groupe d’agents affecté qui identifie les agents qui peuvent recevoir des appels pour le groupe Response Group. Pour créer un groupe d’agents, vous pouvez définir un groupe personnalisé en sélectionnant des utilisateurs éligibles. Les utilisateurs éligibles sont activés pour Skype Entreprise Server et Voix Entreprise.
ms.openlocfilehash: 3c79d46096a39cde01ea4c3246f71b972933c4d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829144"
---
# <a name="select-agents"></a><span data-ttu-id="72a3d-106">Sélection des agents</span><span class="sxs-lookup"><span data-stu-id="72a3d-106">Select Agents</span></span>

<span data-ttu-id="72a3d-107">Les agents sont des utilisateurs désignés pour répondre aux appels Response Group.</span><span class="sxs-lookup"><span data-stu-id="72a3d-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="72a3d-108">Les groupes Response Group doivent avoir un groupe d’agents affecté qui identifie les agents qui peuvent recevoir des appels pour le groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="72a3d-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="72a3d-109">Pour créer un groupe d’agents, vous pouvez définir un groupe personnalisé en sélectionnant des utilisateurs éligibles.</span><span class="sxs-lookup"><span data-stu-id="72a3d-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="72a3d-110">Les utilisateurs éligibles sont activés pour Skype Entreprise Server et Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="72a3d-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="72a3d-111">La boîte de dialogue **Sélectionner des agents** permet de sélectionner les utilisateurs à ajouter à un groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="72a3d-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="72a3d-112">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="72a3d-112">UI Reference</span></span>

<span data-ttu-id="72a3d-113">La liste suivante décrit les contrôles de la boîte de dialogue Sélectionner des **agents.**</span><span class="sxs-lookup"><span data-stu-id="72a3d-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="72a3d-114">**Rechercher** Recherche l’adresse SIP ou le nom complet d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="72a3d-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="72a3d-115">Entrez tout ou partie de l’adresse ou du nom.</span><span class="sxs-lookup"><span data-stu-id="72a3d-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="72a3d-116">Laissez la zone de recherche vide pour afficher tous les utilisateurs activés pour Skype Entreprise Server et Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="72a3d-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="72a3d-117">**Nombre maximal d’utilisateurs à afficher** Modifie le nombre de résultats renvoyés qui sont affichés.</span><span class="sxs-lookup"><span data-stu-id="72a3d-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="72a3d-118">Utilisez ce compteur pour limiter la recherche si vous attendez de nombreux résultats.</span><span class="sxs-lookup"><span data-stu-id="72a3d-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="72a3d-119">La liste suivante décrit les champs de la boîte de dialogue Sélectionner des **agents.**</span><span class="sxs-lookup"><span data-stu-id="72a3d-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="72a3d-120">**Agent** Affiche les noms d’utilisateur renvoyés par la recherche.</span><span class="sxs-lookup"><span data-stu-id="72a3d-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="72a3d-121">**Adresse SIP** Affiche les adresses SIP de l’utilisateur renvoyées par la recherche.</span><span class="sxs-lookup"><span data-stu-id="72a3d-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="72a3d-122">**Téléphonie** Affiche la valeur du champ **Téléphonie** défini pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="72a3d-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="72a3d-123">**Activé** Affiche la valeur du **champ Activé pour Lync Server** défini pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="72a3d-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="72a3d-124">Pour plus d’informations sur l’utilisation des groupes d’agents, voir [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="72a3d-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


