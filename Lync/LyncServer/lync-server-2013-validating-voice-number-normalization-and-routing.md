---
title: 'Lync Server 2013 : validation de la normalisation et du routage des numéros vocaux'
description: 'Lync Server 2013 : validation de la normalisation et du routage des numéros vocaux.'
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
ms.openlocfilehash: 5f28f679cbb991bdb90362eb61c9c7b68879791e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547140"
---
# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="69874-103">Validation de la normalisation et du routage des numéros vocaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69874-103">Validating voice number normalization and routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69874-104">_**Dernière modification de la rubrique :** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="69874-104">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="69874-105">La normalisation des numéros et le routage sont très importants pour l’environnement voix entreprise fonctionnel.</span><span class="sxs-lookup"><span data-stu-id="69874-105">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="69874-106">En particulier lors des migrations de PBX vers un environnement Lync Server autonome, l’une des clés de la migration est de révéler et de documenter toutes les règles de numérotation existantes, et de créer des règles de normalisation appropriées, des stratégies de voix, des utilisations de téléphone et des itinéraires.</span><span class="sxs-lookup"><span data-stu-id="69874-106">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="69874-107">La validation de la normalisation et du routage des nombres est importante non seulement pendant les migrations, mais aussi pendant une opération normale et stable du système.</span><span class="sxs-lookup"><span data-stu-id="69874-107">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="69874-108">Nous vous recommandons d’effectuer cette validation tous les jours à l’aide du panneau de configuration Lync Server, en commençant par le développement d’un ensemble robuste de cas de test par rapport à l’ensemble actuel de règles de normalisation publiées dans les paramètres globaux de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69874-108">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="69874-109">Ces cas de test doivent être exécutés tous les jours pour mettre en évidence les modifications non souhaitées qui ont été apportées au plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="69874-109">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="69874-110">Le panneau de configuration Lync Server vous permet également de visualiser, de tester, de modifier, d’archiver et de partager des informations de configuration sur le routage des communications vocales et de modifier les règles de normalisation des numéros de voix de l’entreprise, les plans de numérotation, la stratégie de voix et les itinéraires.</span><span class="sxs-lookup"><span data-stu-id="69874-110">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="69874-111">Il comporte des fonctionnalités supplémentaires permettant d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="69874-111">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="69874-112">L’exportation et l’importation de données de routage des communications vocales entre les systèmes ;</span><span class="sxs-lookup"><span data-stu-id="69874-112">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="69874-113">Test des modifications de configuration avant leur téléchargement vers un système actif.</span><span class="sxs-lookup"><span data-stu-id="69874-113">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="69874-114">La création et l’exécution de cas de test de configuration pour garantir la convivialité des données de routage après les avoir modifiées, mais avant de les soumettre à un système déployé.</span><span class="sxs-lookup"><span data-stu-id="69874-114">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="69874-115">Création et modification des règles de normalisation des numéros, des profils d’emplacement, de la stratégie de voix et des données de routage sans avoir à écrire les expressions régulières nécessaires.</span><span class="sxs-lookup"><span data-stu-id="69874-115">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="69874-116">Analyse d’un profil d’emplacement pour la compatibilité avec Lync Server Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="69874-116">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="69874-117">Vous trouverez plus d’informations sur les tests de routage des communications vocales [dans test de routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="69874-117">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="69874-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="69874-118">See Also</span></span>


[<span data-ttu-id="69874-119">Tester le routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69874-119">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

