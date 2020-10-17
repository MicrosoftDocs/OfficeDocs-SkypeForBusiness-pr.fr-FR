---
title: 'Lync Server 2013 : configuration du parcage d’appel'
description: 'Lync Server 2013 : configuration du parcage d’appel.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2708f26fae5706afc31aa195b9fdb82536247b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568750"
---
# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="e4930-103">Configuration du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4930-103">Configuring Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4930-104">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="e4930-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="e4930-105">Parcage d’appel permet à un utilisateur de voix entreprise de mettre un appel en attente à partir d’un téléphone, puis de récupérer l’appel plus tard en composant un numéro interne (appelé *orbite*de parcage d’appel) à partir de n’importe quel téléphone.</span><span class="sxs-lookup"><span data-stu-id="e4930-105">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="e4930-106">Les composants utilisés par le parcage d’appel sont automatiquement installés et activés sur le serveur frontal ou le serveur Standard Edition lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="e4930-106">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e4930-107">Toutefois, vous devez configurer le parcage d’appel pour qu’il soit disponible pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e4930-107">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="e4930-108">Cette section vous guide tout au long de la configuration du parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="e4930-108">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e4930-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e4930-109">In This Section</span></span>

  - [<span data-ttu-id="e4930-110">Conditions préalables et droits d’utilisateur pour la configuration du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4930-110">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="e4930-111">Processus de déploiement du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4930-111">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="e4930-112">Configuration de la table d’orbites de parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4930-112">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="e4930-113">Configurer les paramètres de parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4930-113">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="e4930-114">Personnalisation de l’attente musicale du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4930-114">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="e4930-115">Activer le parcage d’appel pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4930-115">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="e4930-116">Vérifier les règles de normalisation pour le parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4930-116">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="e4930-117">Module Vérifier le déploiement du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4930-117">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

