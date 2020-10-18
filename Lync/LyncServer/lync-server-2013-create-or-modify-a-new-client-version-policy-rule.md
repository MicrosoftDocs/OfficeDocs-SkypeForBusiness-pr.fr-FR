---
title: 'Lync Server 2013 : création ou modification d’une règle de stratégie de version du client'
description: 'Lync Server 2013 : création ou modification d’une règle de stratégie de version du client.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11ebcf17d5cb14fd519fba8ad36be10894fabdb9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574620"
---
# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="b7159-103">Création ou modification d’une nouvelle règle de stratégie de version des clients dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7159-103">Create or modify a new client version policy rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7159-104">_**Dernière modification de la rubrique :** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="b7159-104">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="b7159-105">Les règles de stratégie de version des clients définissent les actions à entreprendre lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.</span><span class="sxs-lookup"><span data-stu-id="b7159-105">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="b7159-106">Vous pouvez créer ou modifier des règles individuelles pour une stratégie de version de client à partir du panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7159-106">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b7159-107">Les règles sont répertoriées par ordre de priorité.</span><span class="sxs-lookup"><span data-stu-id="b7159-107">Rules are listed in order of precedence.</span></span> <span data-ttu-id="b7159-108">Par exemple, si vous avez une règle qui permet aux clients exécutant la version 1,5 de se connecter, suivi d’une règle qui bloque les clients exécutant une version antérieure à 2,0, la première règle prend la priorité et les clients exécutant la version 1,5 sont autorisés à se connecter.</span><span class="sxs-lookup"><span data-stu-id="b7159-108">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="b7159-109">Pour créer ou modifier des règles de stratégie de version des clients à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="b7159-109">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b7159-110">[Créez ou modifiez une nouvelle stratégie de version du client dans Lync server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) avec le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b7159-110">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="b7159-111">Sur la page **modifier la stratégie de version du client** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b7159-111">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b7159-112">Cliquez sur **Nouveau** pour créer une règle de version du client.</span><span class="sxs-lookup"><span data-stu-id="b7159-112">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="b7159-113">Cliquez sur l’un des types de clients définis dans la liste, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b7159-113">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7159-114">Vous pouvez utiliser des caractères génériques pour spécifier le type du client.</span><span class="sxs-lookup"><span data-stu-id="b7159-114">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="b7159-115">Dans **Agent utilisateur**, sélectionnez un type de client.</span><span class="sxs-lookup"><span data-stu-id="b7159-115">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="b7159-116">Sous **Numéro de version**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b7159-116">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="b7159-117">Dans **Version principale**, tapez le numéro qui correspond à la version principale du client.</span><span class="sxs-lookup"><span data-stu-id="b7159-117">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="b7159-118">Dans **Version secondaire**, tapez le numéro qui correspond à la version secondaire du client.</span><span class="sxs-lookup"><span data-stu-id="b7159-118">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="b7159-119">Dans **Version**, tapez le numéro qui correspond aux versions principale et secondaire du client.</span><span class="sxs-lookup"><span data-stu-id="b7159-119">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="b7159-120">Dans **Mise à jour**, tapez le numéro qui correspond à la version mise à jour du client.</span><span class="sxs-lookup"><span data-stu-id="b7159-120">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7159-121">Vous pouvez utiliser des caractères génériques pour spécifier le numéro de version du client.</span><span class="sxs-lookup"><span data-stu-id="b7159-121">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="b7159-122">Pour sélectionner l’opération de comparaison à utiliser pour la version du client spécifiée ci-dessus, dans **Opération de comparaison**, cliquez sur l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="b7159-122">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="b7159-123">**Identique à**</span><span class="sxs-lookup"><span data-stu-id="b7159-123">**Same as**</span></span>
    
      - <span data-ttu-id="b7159-124">**N’est pas**</span><span class="sxs-lookup"><span data-stu-id="b7159-124">**Is not**</span></span>
    
      - <span data-ttu-id="b7159-125">**Plus récent que**</span><span class="sxs-lookup"><span data-stu-id="b7159-125">**Newer than**</span></span>
    
      - <span data-ttu-id="b7159-126">**Plus récent ou identique**</span><span class="sxs-lookup"><span data-stu-id="b7159-126">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="b7159-127">**Plus ancien que**</span><span class="sxs-lookup"><span data-stu-id="b7159-127">**Older than**</span></span>
    
      - <span data-ttu-id="b7159-128">**Plus ancien ou identique**</span><span class="sxs-lookup"><span data-stu-id="b7159-128">**Older than or same as**</span></span>

6.  <span data-ttu-id="b7159-129">Pour spécifier l’action à exécuter lorsque les critères définis ci-dessus sont respectés, cliquez sur l’une des options suivantes dans **Action** :</span><span class="sxs-lookup"><span data-stu-id="b7159-129">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="b7159-130">Pour autoriser le client à se connecter, cliquez sur **Autoriser**.</span><span class="sxs-lookup"><span data-stu-id="b7159-130">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="b7159-p103">Pour autoriser le client à se connecter et à recevoir des mises à jour de Windows Server Update Service ou Microsoft Update, cliquez sur **Autoriser et mettre à niveau**. Cette action est uniquement disponible lorsque l’agent utilisateur **OC** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b7159-p103">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**. This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b7159-133">La sélection de cette action entraîne l’affichage d’une notification la prochaine fois que les utilisateurs se connectent à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b7159-133">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="b7159-134">La notification indique qu’une mise à jour est disponible, même si les mises à jour n’ont pas encore été publiées dans le service de mise à jour de Windows Server ou dans Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="b7159-134">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="b7159-135">Pour éviter toute confusion, vous avez tout intérêt à choisir cette action après que des mises à jour ont été mises à disposition uniquement.</span><span class="sxs-lookup"><span data-stu-id="b7159-135">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="b7159-p105">Pour autoriser le client à se connecter et afficher un message sur l’emplacement de téléchargement d’une autre version du client, cliquez sur **Autoriser avec une URL**. Vous indiquerez l’URL ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="b7159-p105">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**. You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="b7159-138">Pour empêcher le client de se connecter, cliquez sur **Bloquer**.</span><span class="sxs-lookup"><span data-stu-id="b7159-138">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="b7159-p106">Pour empêcher le client de se connecter et lui permettre de recevoir des mises à jour de Windows Server Update Service ou Microsoft Update, cliquez sur **Bloquer et mettre à niveau**. Cette action est uniquement disponible lorsque l’agent utilisateur **OC** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b7159-p106">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**. This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="b7159-p107">Pour empêcher le client de se connecter et afficher un message sur l’emplacement de téléchargement d’une autre version du client, cliquez sur **Bloquer avec une URL**. Vous indiquerez l’URL ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="b7159-p107">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**. You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="b7159-143">(Facultatif) Si vous avez cliqué sur **Autoriser avec une URL** ou **Bloquer avec une URL** à l’étape précédente, dans le champ **URL**, tapez l’URL de téléchargement du client que vous souhaitez inclure dans le message.</span><span class="sxs-lookup"><span data-stu-id="b7159-143">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="b7159-144">Cliquez sur **OK**, puis sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="b7159-144">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

