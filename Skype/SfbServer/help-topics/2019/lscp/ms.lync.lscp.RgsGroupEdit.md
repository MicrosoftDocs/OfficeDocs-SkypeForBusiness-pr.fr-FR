---
title: Response Groups créer ou modifier un groupe d’agents existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe de réponse (appelées « agents »), ainsi que les paramètres qui s’appliquent à tous les agents du groupe.
ms.openlocfilehash: bafa1ae490da49c8a4af096129a122315a2a7809
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292618"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="09fbf-103">Groupes Response Group : création d’un groupe d’agents ou modification d’un groupe d’agents existant</span><span class="sxs-lookup"><span data-stu-id="09fbf-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="09fbf-104">Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe de réponse (appelées « agents »), ainsi que les paramètres qui s’appliquent à tous les agents du groupe.</span><span class="sxs-lookup"><span data-stu-id="09fbf-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="09fbf-105">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="09fbf-105">UI Reference</span></span>

<span data-ttu-id="09fbf-106">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="09fbf-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="09fbf-107">**Nom** Chaque groupe d’agents nécessite un nom unique.</span><span class="sxs-lookup"><span data-stu-id="09fbf-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="09fbf-108">Utilisez un nom descriptif qui identifie la fonction du groupe.</span><span class="sxs-lookup"><span data-stu-id="09fbf-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="09fbf-109">Par exemple, le support technique.</span><span class="sxs-lookup"><span data-stu-id="09fbf-109">For example, Help Desk.</span></span>

- <span data-ttu-id="09fbf-110">**Description** Ce champ est facultatif.</span><span class="sxs-lookup"><span data-stu-id="09fbf-110">**Description** This field is optional.</span></span> <span data-ttu-id="09fbf-111">Vous pouvez l’utiliser pour fournir des informations supplémentaires sur le groupe.</span><span class="sxs-lookup"><span data-stu-id="09fbf-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="09fbf-112">**Politique de participation** Spécifiez la façon dont les agents doivent se connecter au groupe réponse:</span><span class="sxs-lookup"><span data-stu-id="09fbf-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="09fbf-p103">Sélectionnez **Informel** pour spécifier que les agents du groupe n’ont pas besoin de se connecter et de se déconnecter. Les agents informels sont connectés automatiquement lorsqu’ils se connectent. Le paramètre par défaut est **Informel**.</span><span class="sxs-lookup"><span data-stu-id="09fbf-p103">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in. The default is **Informal**.</span></span>

  - <span data-ttu-id="09fbf-115">Sélectionnez **formel** pour spécifier que les agents du groupe doivent se connecter et se déconnecter. Lorsque vous sélectionnez cette option, l’agent clique sur un élément de menu dans le client pour ouvrir un navigateur et afficher une console de page Web pour se connecter et se déconnecter.</span><span class="sxs-lookup"><span data-stu-id="09fbf-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="09fbf-116">**Durée de l’alerte (secondes)** Spécifiez le nombre de secondes qui doivent sonner un agent avant de proposer l’appel vers le prochain agent disponible.</span><span class="sxs-lookup"><span data-stu-id="09fbf-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="09fbf-117">La valeur doit être au moins 10 secondes et inférieure à 180 secondes.</span><span class="sxs-lookup"><span data-stu-id="09fbf-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="09fbf-118">La valeur par défaut est 20 secondes.</span><span class="sxs-lookup"><span data-stu-id="09fbf-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="09fbf-119">**Méthode de routage** Sélectionnez la méthode permettant de déterminer l’ordre dans lequel les agents reçoivent des appels:</span><span class="sxs-lookup"><span data-stu-id="09fbf-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="09fbf-120">Sélectionnez **Le plus longuement inactif** pour qu’un nouvel appel soit présenté en premier à l’agent qui a été inactif (dont la présence était **Disponible** ou **Inactif(ve)**) le plus longtemps.</span><span class="sxs-lookup"><span data-stu-id="09fbf-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="09fbf-p105">Sélectionnez **Parallèle** pour qu’un nouvel appel soit présenté à tous les agents disponibles simultanément. L’appel est envoyé au premier agent qui l’accepte.</span><span class="sxs-lookup"><span data-stu-id="09fbf-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="09fbf-123">Sélectionnez **Tourniquet (round robin)** pour qu’un nouvel appel soit présenté à chaque agent, à tour de rôle.</span><span class="sxs-lookup"><span data-stu-id="09fbf-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="09fbf-124">Sélectionnez **Série** pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils apparaissent dans la liste **Agent**.</span><span class="sxs-lookup"><span data-stu-id="09fbf-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="09fbf-125">Sélectionnez **surveillant** pour vous permettre d’effectuer un nouvel appel vers tous les agents connectés et l’application de groupe de réponse en même temps, quelle que soit leur présence actuelle.</span><span class="sxs-lookup"><span data-stu-id="09fbf-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="09fbf-126">Les personnes et les utilisateurs qui sont configurés en tant qu’agents peuvent voir tous les appels en attente et peuvent répondre aux appels en attente dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="09fbf-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="09fbf-127">L’appel est envoyé au premier agent qui l’accepte, et les autres intendants et utilisateurs ne peuvent plus voir l’appel.</span><span class="sxs-lookup"><span data-stu-id="09fbf-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="09fbf-128">**Agent** Dans l’une des manières suivantes, sélectionnez les utilisateurs qui doivent être des agents pour le groupe de réponse:</span><span class="sxs-lookup"><span data-stu-id="09fbf-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="09fbf-129">Sélectionnez **utiliser une liste de distribution de courrier existante** pour utiliser une liste de distribution Exchange.</span><span class="sxs-lookup"><span data-stu-id="09fbf-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="09fbf-130">Tapez l’adresse de messagerie de la liste de distribution dans **Adresse de la liste de distribution**.</span><span class="sxs-lookup"><span data-stu-id="09fbf-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09fbf-p108">Vous pouvez sélectionner une seule liste de distribution pour un groupe d’agents. Si la liste de distribution inclut des listes de distribution imbriquées, ces dernières ne sont pas incluses dans le groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="09fbf-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09fbf-133">L’ordre dans lequel les agents sont répertoriés dans la liste de distribution affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet.</span><span class="sxs-lookup"><span data-stu-id="09fbf-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09fbf-134">Les appartenances ou listes masquées masquées peuvent être visibles par les administrateurs ou les utilisateurs du groupe réponse.</span><span class="sxs-lookup"><span data-stu-id="09fbf-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="09fbf-135">Pour plus d’informations, reportez-vous à [créer ou modifier un groupe d’agents dans Skype entreprise](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span><span class="sxs-lookup"><span data-stu-id="09fbf-135">For details, see [Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="09fbf-p110">Sélectionnez **Définir un groupe personnalisé d’agents** pour sélectionner les utilisateurs à affecter comme agents pour le groupe de réponse. Cliquez sur **Sélectionner** pour ajouter un agent à la liste. Cliquez sur **Supprimer** pour supprimer un agent sélectionné de la liste.</span><span class="sxs-lookup"><span data-stu-id="09fbf-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="09fbf-p111">Les flèches Haut et Bas déplacent un agent sélectionné vers le haut ou vers le bas dans la liste des agents. L’ordre des agents dans la liste affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet.</span><span class="sxs-lookup"><span data-stu-id="09fbf-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="09fbf-141">Pour plus d’informations sur les fonctionnalités et les fonctionnalités des groupes de réponse, voir [planifier l’application Response Group dans Skype entreprise Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="09fbf-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="09fbf-142">Pour plus d’informations sur l’utilisation des groupes d’agents, reportez-vous à la rubrique [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="09fbf-142">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


