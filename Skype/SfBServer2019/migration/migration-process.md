---
title: Processus de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La procédure de migration recommandée et prise en charge pour Skype entreprise Server 2019 est une migration côte à côte. Cette rubrique décrit les raisons pour lesquelles vous devez utiliser la migration côte à côte et inclut des informations sur les tests de coexistence.
ms.openlocfilehash: 7d8ce6513535871939894092850ad0526b1b6a63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813412"
---
# <a name="migration-process"></a><span data-ttu-id="b0a5b-104">Processus de migration</span><span class="sxs-lookup"><span data-stu-id="b0a5b-104">Migration process</span></span>

<span data-ttu-id="b0a5b-105">La procédure de migration recommandée et prise en charge pour Skype entreprise Server 2019 est une migration côte à côte.</span><span class="sxs-lookup"><span data-stu-id="b0a5b-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="b0a5b-106">Cette rubrique décrit les raisons pour lesquelles vous devez utiliser la migration côte à côte et inclut des informations sur les tests de coexistence.</span><span class="sxs-lookup"><span data-stu-id="b0a5b-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="b0a5b-107">Migration côte à côte</span><span class="sxs-lookup"><span data-stu-id="b0a5b-107">Side-By-Side Migration</span></span>

<span data-ttu-id="b0a5b-108">Dans presque chaque migration, utilisez le chemin de migration côte à côte.</span><span class="sxs-lookup"><span data-stu-id="b0a5b-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="b0a5b-109">Dans le cas d’une migration côte à côte, vous déployez un nouveau serveur avec Skype entreprise Server 2019, parallèlement à un serveur correspondant exécutant une version antérieure, puis transférez les opérations vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="b0a5b-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="b0a5b-110">S’il est nécessaire de revenir à la version précédente, il est nécessaire de basculer vers les serveurs d’origine.</span><span class="sxs-lookup"><span data-stu-id="b0a5b-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="b0a5b-111">Notez que dans ce cas, toutes les réunions planifiées avec des clients mis à niveau ne fonctionneront pas et les clients devront également être mis à niveau vers une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="b0a5b-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="b0a5b-112">Tests de coexistence</span><span class="sxs-lookup"><span data-stu-id="b0a5b-112">Coexistence Testing</span></span>

<span data-ttu-id="b0a5b-113">Après avoir déployé Skype entreprise Server 2019 parallèlement à la version précédente, le déploiement représente un état de test de coexistence de Skype entreprise Server 2019 et la version précédente.</span><span class="sxs-lookup"><span data-stu-id="b0a5b-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="b0a5b-114">Dans cet État, il est important de tester et de veiller à ce que les services soient démarrés, chaque site peut être administré et les clients peuvent communiquer avec leurs utilisateurs actuels et propriétaires.</span><span class="sxs-lookup"><span data-stu-id="b0a5b-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="b0a5b-115">Avant de procéder à la migration de tous les utilisateurs, il est très important de comprendre l’état de chacun d’eux et de garantir le fonctionnement correct de chaque déploiement.</span><span class="sxs-lookup"><span data-stu-id="b0a5b-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="b0a5b-116">En règle générale, la phase de test de coexistence existe tout au long des tests pilotes de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b0a5b-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="b0a5b-117">Les anciens utilisateurs sont déplacés vers Skype entreprise Server 2019 pendant un certain temps pour garantir la compatibilité et les fonctionnalités de l’application.</span><span class="sxs-lookup"><span data-stu-id="b0a5b-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="b0a5b-118">Après le test pilote, les utilisateurs et les applications sont déplacés vers la version de production de Skype entreprise Server 2019, et les applications et les pools hérités de la version précédente sont obsolètes.</span><span class="sxs-lookup"><span data-stu-id="b0a5b-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
