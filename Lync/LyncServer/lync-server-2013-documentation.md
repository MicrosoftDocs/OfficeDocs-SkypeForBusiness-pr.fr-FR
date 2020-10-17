---
title: 'Lync Server 2013 : documentation'
description: 'Lync Server 2013 : documentation.'
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
ms.openlocfilehash: f128daa7941db8ae461b4bb12bcc9b97bbb5876e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553210"
---
# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="52e80-103">Documentation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52e80-103">Documentation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52e80-104">_**Dernière modification de la rubrique :** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="52e80-104">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="52e80-105">Le modèle MOF est composé de nombreuses fonctions de gestion de service.</span><span class="sxs-lookup"><span data-stu-id="52e80-105">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="52e80-106">La documentation sur la manière et le moment où les tâches sont effectuées peuvent être partagées avec les membres de la même équipe ou avec d’autres équipes.</span><span class="sxs-lookup"><span data-stu-id="52e80-106">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="52e80-107">La méthode de stockage et de partage de la documentation peut varier en fonction du type de fonction.</span><span class="sxs-lookup"><span data-stu-id="52e80-107">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="52e80-108">Par exemple, les procédures pour l’administration du système peuvent être stockées sous forme de documents Word, car elles sont généralement imprimées et référencées fréquemment.</span><span class="sxs-lookup"><span data-stu-id="52e80-108">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="52e80-109">Les informations de gestion de la configuration peuvent être automatiquement générées et stockées dans une base de données pour faciliter la recherche et l’indexation.</span><span class="sxs-lookup"><span data-stu-id="52e80-109">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="52e80-110">Une partie de la documentation peut être sensible et doit être restreinte.</span><span class="sxs-lookup"><span data-stu-id="52e80-110">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="52e80-111">Systèmes de gestion des documents</span><span class="sxs-lookup"><span data-stu-id="52e80-111">Document management systems</span></span>

<span data-ttu-id="52e80-112">Un système de gestion de la documentation agit comme un référentiel central pour les documents et permet de s’assurer que seule la dernière révision d’un document est disponible.</span><span class="sxs-lookup"><span data-stu-id="52e80-112">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="52e80-113">Vous pouvez également envisager d’archiver l’ancienne version du document à des fins de référence.</span><span class="sxs-lookup"><span data-stu-id="52e80-113">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="52e80-114">Lync Server fournit des fonctionnalités adaptées à cette tâche.</span><span class="sxs-lookup"><span data-stu-id="52e80-114">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="52e80-115">Databases</span><span class="sxs-lookup"><span data-stu-id="52e80-115">Databases</span></span>

<span data-ttu-id="52e80-116">Plusieurs outils et fonctions de gestion ont été abordés et sont adaptés à l’utilisation des bases de données.</span><span class="sxs-lookup"><span data-stu-id="52e80-116">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="52e80-117">Le processus de gestion de la configuration utilise probablement des processus automatisés qui stockent de grandes quantités de données qui nécessitent l’indexation et la recherche.</span><span class="sxs-lookup"><span data-stu-id="52e80-117">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="52e80-118">Le personnel de support peut rechercher une base de données de problèmes et de résolutions antérieurs lors du dépannage de nouveaux problèmes.</span><span class="sxs-lookup"><span data-stu-id="52e80-118">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="52e80-119">Il est probable que des bases de données différentes seront utilisées à différentes fins.</span><span class="sxs-lookup"><span data-stu-id="52e80-119">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="52e80-120">Déterminez si ces bases de données doivent être liées ou combinées.</span><span class="sxs-lookup"><span data-stu-id="52e80-120">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="52e80-121">Par exemple, si le service d’assistance identifie plusieurs problèmes avec un thème commun (par exemple, un nouveau logiciel provoquant un problème avec une carte réseau spécifique), le personnel du support technique peut interroger la base de données de configuration pour prédire le nombre d’ordinateurs susceptibles d’être affectés.</span><span class="sxs-lookup"><span data-stu-id="52e80-121">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

