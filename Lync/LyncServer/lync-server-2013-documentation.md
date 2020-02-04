---
title: 'Lync Server 2013 : documentation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Documentation
ms:assetid: 5a69c0a2-0986-49c3-809c-89bc175a34ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720335(v=OCS.15)
ms:contentKeyID: 63969609
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6eaeb06f1d9144d0c6f28984d509b3777673e10f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="302e1-102">Documentation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="302e1-102">Documentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="302e1-103">_**Dernière modification de la rubrique :** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="302e1-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="302e1-104">Le modèle MOF est composé de nombreuses fonctions de gestion de service.</span><span class="sxs-lookup"><span data-stu-id="302e1-104">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="302e1-105">La documentation relative au mode d’exécution des tâches peut être partagée avec les membres de la même équipe ou avec d’autres équipes.</span><span class="sxs-lookup"><span data-stu-id="302e1-105">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="302e1-106">Le mode de stockage et de partage de la documentation peut varier en fonction du type de fonction.</span><span class="sxs-lookup"><span data-stu-id="302e1-106">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="302e1-107">Par exemple, les procédures d’administration du système peuvent être stockées en tant que documents Word, car elles sont susceptibles d’être imprimées et référencées fréquemment.</span><span class="sxs-lookup"><span data-stu-id="302e1-107">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="302e1-108">Les informations de gestion de la configuration sont générées automatiquement et stockées dans une base de données pour faciliter la recherche et l’indexation.</span><span class="sxs-lookup"><span data-stu-id="302e1-108">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="302e1-109">La documentation peut être sensible et être limitée.</span><span class="sxs-lookup"><span data-stu-id="302e1-109">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="302e1-110">Systèmes de gestion des documents</span><span class="sxs-lookup"><span data-stu-id="302e1-110">Document management systems</span></span>

<span data-ttu-id="302e1-111">Un système de gestion de la documentation repose sur un référentiel centralisé pour les documents et permet de garantir que seule la dernière version d’un document est disponible.</span><span class="sxs-lookup"><span data-stu-id="302e1-111">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="302e1-112">Vous pouvez également envisager d’archiver l’ancienne version du document pour référence.</span><span class="sxs-lookup"><span data-stu-id="302e1-112">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="302e1-113">Lync Server fournit des fonctionnalités adaptées à cette tâche.</span><span class="sxs-lookup"><span data-stu-id="302e1-113">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="302e1-114">Bases de données</span><span class="sxs-lookup"><span data-stu-id="302e1-114">Databases</span></span>

<span data-ttu-id="302e1-115">Plusieurs outils et fonctions de gestion ayant été abordés et adaptés à l’utilisation de bases de données.</span><span class="sxs-lookup"><span data-stu-id="302e1-115">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="302e1-116">Le processus de gestion de la configuration est susceptible d’utiliser des processus automatisés qui stockent de grandes quantités de données qui nécessitent une indexation et une recherche.</span><span class="sxs-lookup"><span data-stu-id="302e1-116">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="302e1-117">Le personnel du support technique risque de rechercher des problèmes et des résolutions anciens lors de la résolution de nouveaux problèmes.</span><span class="sxs-lookup"><span data-stu-id="302e1-117">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="302e1-118">Il est probable qu’une base de données soit utilisée à différentes fins.</span><span class="sxs-lookup"><span data-stu-id="302e1-118">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="302e1-119">Déterminez s’il est possible de lier ou combiner ces bases de données.</span><span class="sxs-lookup"><span data-stu-id="302e1-119">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="302e1-120">Par exemple, si le service d’assistance identifie plusieurs problèmes liés à un thème courant (par exemple, un nouveau logiciel entraînant un problème avec une carte réseau particulière), l’équipe de support technique peut interroger la base de données de configuration pour prévoir le nombre d’ordinateurs susceptibles d’être touchés.</span><span class="sxs-lookup"><span data-stu-id="302e1-120">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

