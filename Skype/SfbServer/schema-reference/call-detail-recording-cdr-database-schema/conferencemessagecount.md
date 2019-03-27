---
title: Table ConferenceMessageCount dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Chaque enregistrement de la table représente un utilisateur dans une conférence par messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur. Chaque conférence est représenté par plusieurs enregistrements dans ce tableau ; un enregistrement pour chaque utilisateur.
ms.openlocfilehash: 60fa79de17c2db14116bd0ffe211e25a61ec9136
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874356"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6f814-104">Table ConferenceMessageCount dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6f814-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6f814-105">Chaque enregistrement de la table représente un utilisateur dans une conférence par messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6f814-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="6f814-106">Chaque conférence est représenté par plusieurs enregistrements dans ce tableau ; un enregistrement pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6f814-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="6f814-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="6f814-107">**Column**</span></span>|<span data-ttu-id="6f814-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="6f814-108">**Data Type**</span></span>|<span data-ttu-id="6f814-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="6f814-109">**Key/Index**</span></span>|<span data-ttu-id="6f814-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="6f814-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6f814-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="6f814-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="6f814-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="6f814-112">datetime</span></span>  <br/> |<span data-ttu-id="6f814-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="6f814-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6f814-114">Heure de l’instance de la conférence.</span><span class="sxs-lookup"><span data-stu-id="6f814-114">Time of conference instance.</span></span> <span data-ttu-id="6f814-115">Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une instance de la conférence.</span><span class="sxs-lookup"><span data-stu-id="6f814-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="6f814-116">Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="6f814-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6f814-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="6f814-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="6f814-118">int</span><span class="sxs-lookup"><span data-stu-id="6f814-118">int</span></span>  <br/> |<span data-ttu-id="6f814-119">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="6f814-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6f814-120">Numéro d’identification pour identifier l’instance de la conférence.</span><span class="sxs-lookup"><span data-stu-id="6f814-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="6f814-121">Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une instance de la conférence.</span><span class="sxs-lookup"><span data-stu-id="6f814-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="6f814-122">Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="6f814-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6f814-123">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="6f814-123">**UserId**</span></span> <br/> |<span data-ttu-id="6f814-124">int</span><span class="sxs-lookup"><span data-stu-id="6f814-124">int</span></span>  <br/> |<span data-ttu-id="6f814-125">Étrangère</span><span class="sxs-lookup"><span data-stu-id="6f814-125">Foreign</span></span>  <br/> |<span data-ttu-id="6f814-126">Numéro unique identifiant cet utilisateur, référencé à partir de la [table des utilisateurs](users.md).</span><span class="sxs-lookup"><span data-stu-id="6f814-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="6f814-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="6f814-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="6f814-128">smallint</span><span class="sxs-lookup"><span data-stu-id="6f814-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="6f814-129">Le nombre de messages envoyés par cet utilisateur durant cette conférence.</span><span class="sxs-lookup"><span data-stu-id="6f814-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

