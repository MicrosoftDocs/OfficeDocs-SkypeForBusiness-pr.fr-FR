---
title: Modèle d’utilisateur de conférence Lync Server 2013
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
ms.openlocfilehash: 4f517e6d3ea3a832c4331377fa49ef7e474377de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="fdcdd-102">Le modèle utilisateur de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdcdd-102">The conferencing user model in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdcdd-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="fdcdd-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="fdcdd-104">La taille de la réunion est une partie essentielle du modèle utilisateur de conférence de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fdcdd-104">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="fdcdd-105">Après la collecte des données à partir de plusieurs points de données (comme décrit dans la section précédente), nous avons déterminé les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="fdcdd-105">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="fdcdd-106">La plupart des réunions sont en fait de petites réunions en équipe avec une moyenne de quatre à six participants.</span><span class="sxs-lookup"><span data-stu-id="fdcdd-106">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="fdcdd-107">Environ 80% des réunions ont moins de 20 participants.</span><span class="sxs-lookup"><span data-stu-id="fdcdd-107">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="fdcdd-108">99,98% des réunions ont moins de 100 participants.</span><span class="sxs-lookup"><span data-stu-id="fdcdd-108">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="fdcdd-109">En plus de la taille de la réunion, le modèle utilisateur de conférence prend également en compte plusieurs facteurs, tels que :</span><span class="sxs-lookup"><span data-stu-id="fdcdd-109">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="fdcdd-110">**Réunions simultanées**   combien d’utilisateurs sont-ils censés avoir en même temps des réunions ?</span><span class="sxs-lookup"><span data-stu-id="fdcdd-110">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="fdcdd-111">**Media Mix**   quels types de médias sont disponibles et censés être utilisés par les utilisateurs dans les réunions ?</span><span class="sxs-lookup"><span data-stu-id="fdcdd-111">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="fdcdd-112">**Les types**   d’utilisateurs sont des utilisateurs internes, des utilisateurs distants, des utilisateurs fédérés ou des utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="fdcdd-112">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="fdcdd-113">**Durée**   de la réunion avec le temps nécessaire pour permettre à tous les utilisateurs d’une réunion de participer à une réunion ?</span><span class="sxs-lookup"><span data-stu-id="fdcdd-113">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="fdcdd-114">Pour plus d’informations sur le modèle utilisateur, voir [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="fdcdd-114">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="fdcdd-115">Pour déterminer le nombre de réunions et d’utilisateurs à utiliser pour le test, nous avons effectué les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdcdd-115">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="fdcdd-116">A suivi le nombre total d’utilisateurs au sein d’une organisation (par exemple, les utilisateurs 80 000) et multiplié par le taux de concurrence de la réunion (par exemple, 5% de l’ensemble des utilisateurs) pour déterminer le nombre total d’utilisateurs censés participer à des réunions en même temps (dans cet exemple, , 4000 utilisateurs).</span><span class="sxs-lookup"><span data-stu-id="fdcdd-116">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="fdcdd-117">Divisez le nombre total d’utilisateurs par le nombre de serveurs Lync Server 2013, serveurs frontaux du déploiement (par exemple, 8 serveurs) pour déterminer le nombre estimé de participants de la réunion par serveur frontal (dans cet exemple, 500 utilisateurs par serveur frontal).</span><span class="sxs-lookup"><span data-stu-id="fdcdd-117">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="fdcdd-118">Divisez le nombre d’utilisateurs par serveur frontal en fonction de la taille de la réunion moyenne (par exemple, 4 utilisateurs) pour déterminer le nombre de réunions moyenne estimée par serveur frontal (dans cet exemple, les réunions 125 par serveur principal).</span><span class="sxs-lookup"><span data-stu-id="fdcdd-118">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="fdcdd-119">Pour obtenir la charge de média par chaque serveur frontal, nous avons estimé la combinaison de médias.</span><span class="sxs-lookup"><span data-stu-id="fdcdd-119">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="fdcdd-120">Par exemple, en supposant que 75% des réunions nécessitent plus qu’une prise en charge du son et 50% de celles-ci nécessitent le partage d’application, une moyenne de 47 réunions et des utilisateurs 188 se connectent à chaque serveur frontal pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="fdcdd-120">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="fdcdd-121">A testé une large gamme de tailles de réunion (en fonction de notre modèle utilisateur d’un maximum de 250 utilisateurs dans un pool partagé) pour s’assurer de l’évolutivité du serveur.</span><span class="sxs-lookup"><span data-stu-id="fdcdd-121">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

