---
title: 'Lync Server 2013 : Configuration du parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69e2a1c6ef9da447688ea1ca7d0308afc0b4ab9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="3bfc1-102">Configuration du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bfc1-102">Configuring Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bfc1-103">_**Dernière modification de la rubrique:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="3bfc1-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="3bfc1-104">Le parc d’appels permet à un utilisateur d’entreprise Voice de mettre un appel en attente d’un seul téléphone, puis de récupérer l’appel ultérieurement en composant un numéro interne ( \*\* connu sous le nom de bobine de parking) depuis n’importe quel téléphone.</span><span class="sxs-lookup"><span data-stu-id="3bfc1-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="3bfc1-105">Les composants utilisés par le parc d’appels sont automatiquement installés et activés sur le serveur frontal ou le serveur Standard Edition lors du déploiement d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3bfc1-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="3bfc1-106">Toutefois, vous devez configurer le parc d’appels avant qu’il soit disponible pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3bfc1-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="3bfc1-107">Cette section vous guide dans la configuration du parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="3bfc1-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3bfc1-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3bfc1-108">In This Section</span></span>

  - [<span data-ttu-id="3bfc1-109">Conditions prérequises pour la configuration du parcage d’appel et des droits utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bfc1-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="3bfc1-110">Processus de déploiement du parc d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bfc1-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="3bfc1-111">Configuration de la table d’orbites de parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bfc1-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="3bfc1-112">Configurer les paramètres de parc d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bfc1-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="3bfc1-113">Personnaliser le parc d’appels en attente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bfc1-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="3bfc1-114">Activer le parc d’appels pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bfc1-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="3bfc1-115">Vérifier les règles de normalisation du parc d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bfc1-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="3bfc1-116">Facultatif Vérifier le déploiement du parc d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bfc1-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

