---
title: Table ConferenceMessageCount dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Chaque enregistrement de la table représente un utilisateur dans une conférence par messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur. Chaque conférence est représenté par plusieurs enregistrements dans ce tableau ; un enregistrement pour chaque utilisateur.
ms.openlocfilehash: f45de53333b23368351c8c5330b474cd3260192b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901428"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b6741-104">Table ConferenceMessageCount dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b6741-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b6741-105">Chaque enregistrement de la table représente un utilisateur dans une conférence par messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b6741-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="b6741-106">Chaque conférence est représenté par plusieurs enregistrements dans ce tableau ; un enregistrement pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b6741-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="b6741-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b6741-107">**Column**</span></span>|<span data-ttu-id="b6741-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="b6741-108">**Data Type**</span></span>|<span data-ttu-id="b6741-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="b6741-109">**Key/Index**</span></span>|<span data-ttu-id="b6741-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="b6741-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b6741-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="b6741-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="b6741-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b6741-112">datetime</span></span>  <br/> |<span data-ttu-id="b6741-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="b6741-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b6741-114">Heure de l’instance de la conférence.</span><span class="sxs-lookup"><span data-stu-id="b6741-114">Time of conference instance.</span></span> <span data-ttu-id="b6741-115">Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une instance de la conférence.</span><span class="sxs-lookup"><span data-stu-id="b6741-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="b6741-116">Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="b6741-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b6741-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="b6741-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="b6741-118">int</span><span class="sxs-lookup"><span data-stu-id="b6741-118">int</span></span>  <br/> |<span data-ttu-id="b6741-119">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="b6741-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b6741-120">Numéro d’identification pour identifier l’instance de la conférence.</span><span class="sxs-lookup"><span data-stu-id="b6741-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="b6741-121">Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une instance de la conférence.</span><span class="sxs-lookup"><span data-stu-id="b6741-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="b6741-122">Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="b6741-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b6741-123">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="b6741-123">**UserId**</span></span> <br/> |<span data-ttu-id="b6741-124">int</span><span class="sxs-lookup"><span data-stu-id="b6741-124">int</span></span>  <br/> |<span data-ttu-id="b6741-125">Étrangère</span><span class="sxs-lookup"><span data-stu-id="b6741-125">Foreign</span></span>  <br/> |<span data-ttu-id="b6741-126">Numéro unique identifiant cet utilisateur, référencé à partir de la [table des utilisateurs](users.md).</span><span class="sxs-lookup"><span data-stu-id="b6741-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="b6741-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="b6741-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="b6741-128">smallint</span><span class="sxs-lookup"><span data-stu-id="b6741-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="b6741-129">Le nombre de messages envoyés par cet utilisateur durant cette conférence.</span><span class="sxs-lookup"><span data-stu-id="b6741-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

