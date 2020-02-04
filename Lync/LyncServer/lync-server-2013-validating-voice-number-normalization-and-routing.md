---
title: 'Lync Server 2013 : validation de la normalisation et du routage des numéros vocaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16739595878b0c67b37f988295a4b02877a3a6fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="417f1-102">Validation de la normalisation et du routage des numéros vocaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="417f1-102">Validating voice number normalization and routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="417f1-103">_**Dernière modification de la rubrique :** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="417f1-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="417f1-104">Le bon fonctionnement de la normalisation et du routage des numéros est essentiel pour l’environnement d’entreprise voix.</span><span class="sxs-lookup"><span data-stu-id="417f1-104">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="417f1-105">En particulier lors des migrations de l’échange de succursales privées vers un environnement Lync Server autonome, l’une des clés de la migration réussie consiste à afficher et à documenter toutes les règles de numérotation existantes, et à créer des règles de normalisation appropriées, des politiques vocales, utilisations et itinéraires du téléphone.</span><span class="sxs-lookup"><span data-stu-id="417f1-105">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="417f1-106">La validation de la normalisation et de l’acheminement des numéros est important non seulement pendant les migrations, mais également dans le cadre du fonctionnement normal et stable du système.</span><span class="sxs-lookup"><span data-stu-id="417f1-106">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="417f1-107">Nous vous recommandons d’effectuer cette validation quotidiennement en utilisant le panneau de configuration de Lync Server, en commençant par le développement d’un ensemble de scénarios de test puissants par rapport à l’ensemble actuel de règles de normalisation publiées dans les paramètres globaux de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="417f1-107">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="417f1-108">Ces cas de test doivent être exécutés quotidiennement pour mettre en évidence les modifications indésirables apportées et validées au plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="417f1-108">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="417f1-109">Le panneau de configuration de Lync Server vous permet également de visualiser, de tester, de modifier, d’archiver et de partager des informations de configuration sur le routage de la voix et de modifier les règles de normalisation des numéros vocaux d’entreprise, les plans de numérotation, la politique vocale et les itinéraires.</span><span class="sxs-lookup"><span data-stu-id="417f1-109">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="417f1-110">Les fonctionnalités suivantes sont disponibles pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="417f1-110">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="417f1-111">Exportation et importation ou sauvegarde de données de routage de la voix entre systèmes ;</span><span class="sxs-lookup"><span data-stu-id="417f1-111">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="417f1-112">Test de la configuration avant de les télécharger sur un système en direct.</span><span class="sxs-lookup"><span data-stu-id="417f1-112">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="417f1-113">Création et exécution de cas de test de configuration pour garantir la facilité d’utilisation du routage des données après avoir apporté des modifications à celui-ci, mais avant de les valider.</span><span class="sxs-lookup"><span data-stu-id="417f1-113">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="417f1-114">La création et la modification des règles de normalisation des numéros, des profils d’emplacement, de la stratégie vocale et des données de routage sans écrire les expressions régulières nécessaires.</span><span class="sxs-lookup"><span data-stu-id="417f1-114">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="417f1-115">Analyse d’un profil d’emplacement à des fins de compatibilité avec Lync Server Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="417f1-115">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="417f1-116">Vous trouverez des informations supplémentaires sur les tests de routage [de voix dans la boîte de test routage de la voix dans Lync Server 2013](lync-server-2013-test-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="417f1-116">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="417f1-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="417f1-117">See Also</span></span>


[<span data-ttu-id="417f1-118">Test du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="417f1-118">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

