---
title: 'Lync Server 2013 : problèmes avec le test de l’environnement'
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
ms.openlocfilehash: 812796be0589342f346cfc6755ace64cb402f63a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514081"
---
# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="0f42a-102">Problèmes avec le test de l’environnement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f42a-102">Issues with the environment test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f42a-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0f42a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0f42a-104">Best Practices Analyzer vous permet de vérifier que votre environnement Lync Server 2013 est une configuration prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0f42a-104">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="0f42a-105">Dans le cadre des vérifications des services de domaine Active Directory, Best Practices Analyzer permet :</span><span class="sxs-lookup"><span data-stu-id="0f42a-105">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="0f42a-106">de vérifier la préparation de la forêt et du schéma des services de domaine Active Directory ;</span><span class="sxs-lookup"><span data-stu-id="0f42a-106">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="0f42a-107">d’identifier le nombre de domaines et de sites de services de domaine Active Directory du déploiement ;</span><span class="sxs-lookup"><span data-stu-id="0f42a-107">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="0f42a-108">de vérifier les niveaux du domaine et de la forêt ;</span><span class="sxs-lookup"><span data-stu-id="0f42a-108">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="0f42a-109">de vérifier la version du contrôleur de domaine ;</span><span class="sxs-lookup"><span data-stu-id="0f42a-109">Checks the domain controller version.</span></span>

  - <span data-ttu-id="0f42a-110">d’identifier le contexte d’appellation du domaine, de la configuration et du schéma ;</span><span class="sxs-lookup"><span data-stu-id="0f42a-110">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="0f42a-111">d’identifier le nombre d’utilisateurs autorisés ;</span><span class="sxs-lookup"><span data-stu-id="0f42a-111">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="0f42a-112">de vérifier où les paramètres des services de domaine Active Directory sont stockés ;</span><span class="sxs-lookup"><span data-stu-id="0f42a-112">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="0f42a-113">Recherche les points de connexion de service (SCP) pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f42a-113">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="0f42a-114">d’identifier la version de la base de données.</span><span class="sxs-lookup"><span data-stu-id="0f42a-114">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="0f42a-115">Résolution des problèmes avec l’environnement</span><span class="sxs-lookup"><span data-stu-id="0f42a-115">Resolving Issues with the Environment</span></span>

<span data-ttu-id="0f42a-p102">Si l’environnement de test détecte des problèmes avec votre environnement, ces problèmes sont probablement causés par d’autres problèmes avec votre configuration d’Active Directory ou le niveau du logiciel exécuté sur des serveurs spécifiques. Par exemple, si Best Practices Analyzer identifie un contrôleur de domaine de votre environnement exécutant Windows Server 2000, il émettra un avertissement et vous devrez mettre à niveau ces contrôleurs de domaine vers une version prise en charge de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="0f42a-p102">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers. For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

