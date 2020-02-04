---
title: 'Lync Server 2013 : problèmes liés au test de l’environnement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65803ff396a9615787291de2d728fe63f3350d0b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="afaab-102">Problèmes liés au test de l’environnement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afaab-102">Issues with the environment test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afaab-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="afaab-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="afaab-104">Le mode d’analyse des pratiques recommandées vous permet de vérifier que votre environnement Lync Server 2013 est une configuration prise en charge.</span><span class="sxs-lookup"><span data-stu-id="afaab-104">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="afaab-105">Dans le cadre de la vérification des services de domaine Active Directory (AD FS), l’analyseur des recommandations est le suivant :</span><span class="sxs-lookup"><span data-stu-id="afaab-105">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="afaab-106">Vérifie la forêt et la préparation du schéma des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="afaab-106">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="afaab-107">Identifie le nombre de sites et de domaines services de domaine Active Directory du déploiement.</span><span class="sxs-lookup"><span data-stu-id="afaab-107">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="afaab-108">Vérifie les niveaux de forêt et de domaine.</span><span class="sxs-lookup"><span data-stu-id="afaab-108">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="afaab-109">Vérifie la version du contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="afaab-109">Checks the domain controller version.</span></span>

  - <span data-ttu-id="afaab-110">Identifie le contexte de nom de domaine, de configuration et de schéma.</span><span class="sxs-lookup"><span data-stu-id="afaab-110">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="afaab-111">Identifie le nombre d’utilisateurs activés.</span><span class="sxs-lookup"><span data-stu-id="afaab-111">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="afaab-112">Vérifie l’emplacement de stockage des paramètres globaux des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="afaab-112">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="afaab-113">Recherche les points de connexion de service de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afaab-113">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="afaab-114">Identifie la version de la base de données.</span><span class="sxs-lookup"><span data-stu-id="afaab-114">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="afaab-115">Résolution des problèmes liés à l’environnement</span><span class="sxs-lookup"><span data-stu-id="afaab-115">Resolving Issues with the Environment</span></span>

<span data-ttu-id="afaab-116">Si le test de l’environnement a détecté des problèmes avec votre environnement, il est probable que les problèmes liés à votre configuration Active Directory ou au niveau de logiciel exécuté sur des serveurs spécifiques apparaissent.</span><span class="sxs-lookup"><span data-stu-id="afaab-116">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers.</span></span> <span data-ttu-id="afaab-117">Par exemple, si le service d’analyse des pratiques recommandées identifie tout contrôleur de domaine dans votre environnement exécutant Windows Server 2000, il émet un avertissement et vous devrez mettre à niveau ces contrôleurs de domaine vers une version prise en charge de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="afaab-117">For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

