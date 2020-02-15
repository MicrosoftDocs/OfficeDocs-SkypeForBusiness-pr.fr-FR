---
title: Modèle utilisateur de conférence Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcc74259f9a5cb6ee40cb29fbab56e638ba78b79
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="a9455-102">Modèle utilisateur de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9455-102">The conferencing user model in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9455-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="a9455-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="a9455-104">Une partie essentielle du modèle utilisateur de conférence Lync Server est la taille de la réunion.</span><span class="sxs-lookup"><span data-stu-id="a9455-104">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="a9455-105">Après avoir collecté des données à partir de plusieurs points de données (comme indiqué dans la section précédente), nous avons déterminé les points suivants :</span><span class="sxs-lookup"><span data-stu-id="a9455-105">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="a9455-106">La plupart des réunions sont en fait de petites réunions collaboratives, avec une moyenne de quatre à six participants.</span><span class="sxs-lookup"><span data-stu-id="a9455-106">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="a9455-107">Environ 80 % des réunions comptent moins de 20 participants.</span><span class="sxs-lookup"><span data-stu-id="a9455-107">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="a9455-108">99,98 % des réunions comptent moins de 100 participants.</span><span class="sxs-lookup"><span data-stu-id="a9455-108">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="a9455-109">Outre la taille des réunions, le modèle utilisateur des conférences prend également en compte divers facteurs, tels que les suivants :</span><span class="sxs-lookup"><span data-stu-id="a9455-109">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="a9455-110">**Réunions simultanées**   combien d’utilisateurs doivent être en réunion en même temps ?</span><span class="sxs-lookup"><span data-stu-id="a9455-110">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="a9455-111">**Mélange**   de médias quels types de médias sont disponibles et susceptibles d’être utilisés par les utilisateurs dans les réunions ?</span><span class="sxs-lookup"><span data-stu-id="a9455-111">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="a9455-112">**Les types**   d’utilisateur sont les utilisateurs internes, les utilisateurs distants, les utilisateurs fédérés ou les utilisateurs anonymes ?</span><span class="sxs-lookup"><span data-stu-id="a9455-112">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="a9455-113">**Temps**   de fonctionnement de la mise en service de la réunion combien de temps faut-il pour que tous les utilisateurs d’une réunion rejoignent une réunion ?</span><span class="sxs-lookup"><span data-stu-id="a9455-113">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="a9455-114">Pour plus d’informations sur le modèle utilisateur, voir [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="a9455-114">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="a9455-115">Pour déterminer le nombre de réunions et d’utilisateurs à utiliser pour effectuer les tests, nous avons procédé comme suit :</span><span class="sxs-lookup"><span data-stu-id="a9455-115">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="a9455-116">Nous avons pris le nombre total d’utilisateurs d’une organisation (par exemple, 80 000 utilisateurs) que nous avons multiplié par le taux de simultanéité des réunions (par exemple, 5 % de tous les utilisateurs) afin de déterminer le nombre total d’utilisateurs susceptibles d’assister simultanément à des réunions (dans le présent exemple, 4 000 utilisateurs).</span><span class="sxs-lookup"><span data-stu-id="a9455-116">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="a9455-117">Divisé le nombre total d’utilisateurs par le nombre de Lync Server 2013, serveurs frontaux dans le déploiement (par exemple, 8 serveurs) pour déterminer le nombre estimé de participants à la réunion par serveur frontal (dans cet exemple, 500 utilisateurs par serveur frontal).</span><span class="sxs-lookup"><span data-stu-id="a9455-117">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="a9455-118">Divisez le nombre d’utilisateurs par serveur frontal en fonction de la taille moyenne des réunions (par exemple, 4 utilisateurs) pour déterminer le nombre moyen estimé de réunions par serveur frontal (dans cet exemple, 125 réunions par serveur frontal).</span><span class="sxs-lookup"><span data-stu-id="a9455-118">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="a9455-119">Pour obtenir la charge par support sur chaque serveur frontal, nous avons évalué le mixage multimédia.</span><span class="sxs-lookup"><span data-stu-id="a9455-119">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="a9455-120">Par exemple, en supposant que 75% des réunions ont besoin de plus que la prise en charge audio et qu' 50% de ces réunions nécessitent le partage d’application, une moyenne de 47 réunions et de 188 utilisateurs se connectent simultanément à chaque serveur frontal pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="a9455-120">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="a9455-121">Nous avons testé diverses tailles de réunion (en nous basant sur notre modèle utilisateur qui compte un maximum de 250 utilisateurs dans un pool partagé) afin de garantir l’extensibilité du serveur.</span><span class="sxs-lookup"><span data-stu-id="a9455-121">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

