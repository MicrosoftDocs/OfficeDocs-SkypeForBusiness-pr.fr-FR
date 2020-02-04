---
title: 'Lync Server 2013 : Configuration du directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58d0b309e87dddb621d6c3a90b16b6c2e02845df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="8773b-102">Configuration du directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8773b-102">Setting up the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8773b-103">_**Dernière modification de la rubrique :** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="8773b-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="8773b-104">Si vous autorisez l’accès pour les utilisateurs externes en déployant des serveurs Edge, il est possible de déployer un réalisateur.</span><span class="sxs-lookup"><span data-stu-id="8773b-104">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="8773b-105">Un directeur est un serveur exécutant Microsoft Lync Server 2013 qui authentifie les demandes des utilisateurs, mais ne possède pas de compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8773b-105">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="8773b-106">Ce n’est pas une condition requise, mais elle est très utile si vous avez des problèmes de performances et souhaitez rationaliser les demandes d’authentification.</span><span class="sxs-lookup"><span data-stu-id="8773b-106">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="8773b-107">Si vous décidez qu’il s’agit d’une bonne idée de votre organisation, les étapes de configuration d’un directeur ou d’un pool de réalisateurs sont similaires à la configuration d’un pool d’entreprise frontal Enterprise Edition ou d’un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="8773b-107">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="8773b-108">Après avoir défini votre ou vos réalisateurs dans le générateur de topologie, vous devez effectuer les étapes décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="8773b-108">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8773b-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8773b-109">In This Section</span></span>

  - [<span data-ttu-id="8773b-110">Installation du magasin de configurations local dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8773b-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="8773b-111">Installation de Lync Server 2013 sur le directeur</span><span class="sxs-lookup"><span data-stu-id="8773b-111">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="8773b-112">Configuration des certificats pour le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8773b-112">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="8773b-113">Démarrage des services sur le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8773b-113">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="8773b-114">Test du directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8773b-114">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="8773b-115">Configuration de la connexion automatique du client pour utiliser le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8773b-115">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

