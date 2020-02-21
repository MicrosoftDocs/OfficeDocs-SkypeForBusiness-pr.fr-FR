---
title: 'Lync Server 2013 : configuration du directeur'
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
ms.openlocfilehash: 867b267c731f97cc16ff80187e33c776e16c7802
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="ece8b-102">Configuration du directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ece8b-102">Setting up the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ece8b-103">_**Dernière modification de la rubrique :** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="ece8b-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="ece8b-104">Si vous activez l’accès pour les utilisateurs externes en déployant des serveurs Edge, vous pouvez déployer un directeur.</span><span class="sxs-lookup"><span data-stu-id="ece8b-104">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="ece8b-105">Un directeur est un serveur exécutant Microsoft Lync Server 2013 qui authentifie les demandes des utilisateurs, mais n’héberge aucun compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ece8b-105">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="ece8b-106">À présent, cela n’est pas obligatoire, mais il est très utile si vous craignez les performances et que vous souhaitez aider à rationaliser les demandes d’authentification.</span><span class="sxs-lookup"><span data-stu-id="ece8b-106">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="ece8b-107">Si vous décidez qu’il s’agit d’une bonne idée pour votre organisation, les étapes de configuration d’un directeur ou d’un pool directeur sont similaires à la configuration d’un pool frontal Enterprise Edition ou d’un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ece8b-107">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="ece8b-108">Une fois que vous avez défini vos Directors dans le générateur de topologie, vous devez effectuer les étapes décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="ece8b-108">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ece8b-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ece8b-109">In This Section</span></span>

  - [<span data-ttu-id="ece8b-110">Installer le magasin de configurations local dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ece8b-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="ece8b-111">Installation de Lync Server 2013 sur le directeur</span><span class="sxs-lookup"><span data-stu-id="ece8b-111">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="ece8b-112">Configurer des certificats pour le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ece8b-112">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="ece8b-113">Démarrer les services sur le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ece8b-113">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="ece8b-114">Test du directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ece8b-114">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="ece8b-115">Configuration de la connexion automatique du client pour utiliser le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ece8b-115">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

