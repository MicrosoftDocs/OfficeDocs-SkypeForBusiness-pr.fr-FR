---
title: 'Groupes Response Group : création d’un groupe d’agents ou modification d’un groupe d’agents existant'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe Response Group (appelées agents), ainsi que les paramètres qui s’appliquent à tous les agents dans le groupe.
ms.openlocfilehash: 944cd48745a2524ccfcd795d9edc60e806859301
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118963"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="0a19b-103">Services Response Group : création d’un nouveau ou modification d’un groupe existant</span><span class="sxs-lookup"><span data-stu-id="0a19b-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="0a19b-104">Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe Response Group (appelées agents), ainsi que les paramètres qui s’appliquent à tous les agents dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="0a19b-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0a19b-105">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="0a19b-105">UI Reference</span></span>

<span data-ttu-id="0a19b-106">La liste suivante décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="0a19b-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="0a19b-107">**Nom** Chaque groupe d’agents requiert un nom unique.</span><span class="sxs-lookup"><span data-stu-id="0a19b-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="0a19b-108">Utilisez un nom descriptif qui identifie la fonction du groupe.</span><span class="sxs-lookup"><span data-stu-id="0a19b-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="0a19b-109">Par exemple, Help Desk.</span><span class="sxs-lookup"><span data-stu-id="0a19b-109">For example, Help Desk.</span></span>

- <span data-ttu-id="0a19b-110">**Description** Ce champ est facultatif.</span><span class="sxs-lookup"><span data-stu-id="0a19b-110">**Description** This field is optional.</span></span> <span data-ttu-id="0a19b-111">Utilisez-le pour fournir des détails supplémentaires sur le groupe.</span><span class="sxs-lookup"><span data-stu-id="0a19b-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="0a19b-112">**Stratégie de participation** Spécifiez la façon dont les agents se connectent au groupe Response Group :</span><span class="sxs-lookup"><span data-stu-id="0a19b-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="0a19b-113">Sélectionnez **Informel** pour spécifier que les agents du groupe n’ont pas besoin de se connecter et de se sortir. Les agents informels sont automatiquement connectés lorsqu’ils se connectent.</span><span class="sxs-lookup"><span data-stu-id="0a19b-113">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in.</span></span> <span data-ttu-id="0a19b-114">Le paramètre par défaut est **Informel**.</span><span class="sxs-lookup"><span data-stu-id="0a19b-114">The default is **Informal**.</span></span>

  - <span data-ttu-id="0a19b-115">Sélectionnez **Formel** pour spécifier que les agents du groupe doivent se connecter et se sortir. Lorsque vous sélectionnez cette option, les agents cliquent sur un élément de menu dans le client pour ouvrir un navigateur et afficher une console de page web pour la signature et la sortie.</span><span class="sxs-lookup"><span data-stu-id="0a19b-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="0a19b-116">**Temps d’alerte (secondes)** Spécifiez le nombre de secondes de sonnerie d’un agent avant d’appeler l’agent disponible suivant.</span><span class="sxs-lookup"><span data-stu-id="0a19b-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="0a19b-117">La valeur doit être d’au moins 10 secondes et inférieure à 180 secondes.</span><span class="sxs-lookup"><span data-stu-id="0a19b-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="0a19b-118">La valeur par défaut est 20 secondes.</span><span class="sxs-lookup"><span data-stu-id="0a19b-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="0a19b-119">**Méthode de routage** Sélectionnez la méthode pour déterminer l’ordre dans lequel les agents reçoivent des appels :</span><span class="sxs-lookup"><span data-stu-id="0a19b-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="0a19b-120">Sélectionnez **Le plus longuement inactif** pour qu’un nouvel appel soit présenté en premier à l’agent qui a été inactif (dont la présence était **Disponible** ou **Inactive**) le plus longtemps.</span><span class="sxs-lookup"><span data-stu-id="0a19b-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="0a19b-p105">Sélectionnez **Parallèle** pour qu’un nouvel appel soit présenté à tous les agents disponibles simultanément. L’appel est envoyé au premier agent qui l’accepte.</span><span class="sxs-lookup"><span data-stu-id="0a19b-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="0a19b-123">Sélectionnez **Tourniquet (round robin)** pour qu’un nouvel appel soit présenté à chaque agent, à tour de rôle.</span><span class="sxs-lookup"><span data-stu-id="0a19b-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="0a19b-124">Sélectionnez **Série** pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel il apparaît dans la liste **Agent**.</span><span class="sxs-lookup"><span data-stu-id="0a19b-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="0a19b-125">Sélectionnez **Attendant** pour qu’il propose un nouvel appel à tous les agents qui sont inscrits et à l’application Response Group en même temps, quelle que soit leur présence actuelle.</span><span class="sxs-lookup"><span data-stu-id="0a19b-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="0a19b-126">Les attendants et les utilisateurs clients configurés en tant qu’agents peuvent voir tous les appels en attente et répondre aux appels en attente dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="0a19b-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="0a19b-127">L’appel est envoyé au premier agent qui l’accepte, et les autres attendants et utilisateurs ne voient plus l’appel.</span><span class="sxs-lookup"><span data-stu-id="0a19b-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="0a19b-128">**Agents** Sélectionnez les utilisateurs qui doivent être des agents pour le groupe Response Group de l’une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="0a19b-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="0a19b-129">Sélectionnez **Utiliser une liste de distribution** de courrier électronique existante pour utiliser une liste de distribution Exchange.</span><span class="sxs-lookup"><span data-stu-id="0a19b-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="0a19b-130">Tapez l’adresse de messagerie de la liste de distribution dans **Adresse de la liste de distribution**.</span><span class="sxs-lookup"><span data-stu-id="0a19b-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a19b-p108">Vous pouvez sélectionner une seule liste de distribution pour un groupe d’agents. Si la liste de distribution inclut des listes de distribution imbriquées, ces dernières ne sont pas incluses dans le groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="0a19b-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a19b-133">L’ordre dans lequel les agents sont répertoriés dans la liste de distribution affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet.</span><span class="sxs-lookup"><span data-stu-id="0a19b-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a19b-134">Les appartenances masquées ou les listes masquées peuvent devenir visibles pour les administrateurs ou les utilisateurs Response Group.</span><span class="sxs-lookup"><span data-stu-id="0a19b-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="0a19b-135">Pour plus d’informations, [voir Créer ou modifier un groupe d’agents dans Skype Entreprise.](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)</span><span class="sxs-lookup"><span data-stu-id="0a19b-135">For details, see [Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="0a19b-p110">Sélectionnez **Définir un groupe personnalisé d’agents** pour sélectionner les utilisateurs que vous voulez attribuer en tant qu’agents pour le groupe Response Group. Cliquez sur **Sélectionner** pour ajouter un agent à la liste. Cliquez sur **Supprimer** pour supprimer un agent sélectionné de la liste.</span><span class="sxs-lookup"><span data-stu-id="0a19b-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="0a19b-p111">Les flèches Haut et Bas déplacent un agent sélectionné vers le haut et vers le bas dans la liste des agents. L’ordre des agents dans la liste affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet.</span><span class="sxs-lookup"><span data-stu-id="0a19b-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="0a19b-141">Pour plus d’informations sur les fonctionnalités de Response Group, voir [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span><span class="sxs-lookup"><span data-stu-id="0a19b-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="0a19b-142">Pour plus d’informations sur l’utilisation des groupes d’agents, voir [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="0a19b-142">For details about working with agent groups, see [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) in the Operations documentation.</span></span>