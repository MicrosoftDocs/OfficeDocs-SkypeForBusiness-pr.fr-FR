---
title: 'Lync Server 2013 : vérification de la connectivité pour les utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89f1721967ec693556fecd12d31f45b9b3d108d4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="c1c7a-102">Vérifier la connectivité pour les utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1c7a-102">Verify connectivity for external users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1c7a-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c1c7a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c1c7a-104">La validation de la connectivité pour les utilisateurs externes nécessite de s’assurer de la connectivité des utilisateurs vers le serveur et le port pour le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="c1c7a-104">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="c1c7a-105">Le site analyseur de connectivité à distance (<http://www.testocsconnectivity.com>) est une ressource précieuse pour la confirmation de votre configuration et la possibilité de vous connecter, d’envoyer et de recevoir les messages corrects pour les scénarios requis par l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="c1c7a-105">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="c1c7a-106">Le site est géré et géré par le support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c1c7a-106">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="c1c7a-107">Pour accéder à l’Analyseur de connectivité à distance, ouvrez le site web dans un navigateur et suivez les instructions relatives à la sélection du scénario.</span><span class="sxs-lookup"><span data-stu-id="c1c7a-107">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="c1c7a-108">Tester la connectivité des utilisateurs externes et de l’accès externe</span><span class="sxs-lookup"><span data-stu-id="c1c7a-108">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="c1c7a-109">Les tests d’accès des utilisateurs externes doivent inclure tous les types d’utilisateurs externes pris en charge par votre organisation, dont un ou plusieurs des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c1c7a-109">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="c1c7a-110">Utilisateurs d’au moins un domaine fédéré, et test de la messagerie instantanée, de la présence et du partage du Bureau.</span><span class="sxs-lookup"><span data-stu-id="c1c7a-110">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="c1c7a-111">Utilisateurs de chaque fournisseur de services de messagerie instantanée public pris en charge par votre organisation (et pour lequel le provisionnement a été effectué).</span><span class="sxs-lookup"><span data-stu-id="c1c7a-111">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="c1c7a-112">Utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="c1c7a-112">Anonymous users.</span></span>

  - <span data-ttu-id="c1c7a-113">Utilisateurs appartenant à votre organisation, qui sont connectés à Lync à distance, mais qui n’utilisent pas VPN.</span><span class="sxs-lookup"><span data-stu-id="c1c7a-113">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="c1c7a-114">Ces tests déterminent si votre serveur Edge :</span><span class="sxs-lookup"><span data-stu-id="c1c7a-114">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="c1c7a-115">Écoute sur les ports requis à l’aide d’un client telnet depuis l’extérieur de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="c1c7a-115">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="c1c7a-116">Exemple : telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="c1c7a-116">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="c1c7a-117">Effectuez le test précédent sur les ports que vous utilisez sur le serveur Edge ou le pool de serveur Edge en fonction de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="c1c7a-117">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="c1c7a-118">Effectuer une résolution DNS externe précise.</span><span class="sxs-lookup"><span data-stu-id="c1c7a-118">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="c1c7a-p102">Depuis l’extérieur de votre réseau, exécutez la commande ping sur chacun des noms de domaine complets (FQDN) externes de votre serveur Edge ou pool de serveurs Edge. Même si la commande ping échoue, vous obtiendrez les adresses IP que vous pouvez comparer à celles que vous avez affectées.</span><span class="sxs-lookup"><span data-stu-id="c1c7a-p102">From outside your network ping each of the external FQDN’s of your Edge or Edge pool. Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

