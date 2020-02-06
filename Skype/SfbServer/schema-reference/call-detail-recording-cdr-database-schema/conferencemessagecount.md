---
title: Table ConferenceMessageCount dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Chaque enregistrement de cette table représente un utilisateur au sein d’une conférence par messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur. Chaque conférence est représentée par plusieurs enregistrements dans ce tableau ; un enregistrement pour chaque utilisateur.
ms.openlocfilehash: 66651f798d627ef4ea783c4ecf4e7cb8f1adab81
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815372"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="eaf2c-104">Table ConferenceMessageCount dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="eaf2c-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="eaf2c-105">Chaque enregistrement de cette table représente un utilisateur au sein d’une conférence par messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="eaf2c-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="eaf2c-106">Chaque conférence est représentée par plusieurs enregistrements dans ce tableau ; un enregistrement pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="eaf2c-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="eaf2c-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="eaf2c-107">**Column**</span></span>|<span data-ttu-id="eaf2c-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="eaf2c-108">**Data Type**</span></span>|<span data-ttu-id="eaf2c-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="eaf2c-109">**Key/Index**</span></span>|<span data-ttu-id="eaf2c-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="eaf2c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eaf2c-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="eaf2c-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="eaf2c-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="eaf2c-112">datetime</span></span>  <br/> |<span data-ttu-id="eaf2c-113">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="eaf2c-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="eaf2c-114">Durée de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="eaf2c-114">Time of conference instance.</span></span> <span data-ttu-id="eaf2c-115">Utilisé conjointement avec **SessionIdSeq** pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="eaf2c-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="eaf2c-116">Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="eaf2c-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="eaf2c-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="eaf2c-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="eaf2c-118">int</span><span class="sxs-lookup"><span data-stu-id="eaf2c-118">int</span></span>  <br/> |<span data-ttu-id="eaf2c-119">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="eaf2c-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="eaf2c-120">Numéro d’identification pour identifier l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="eaf2c-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="eaf2c-121">Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="eaf2c-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="eaf2c-122">Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="eaf2c-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="eaf2c-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="eaf2c-123">**UserId**</span></span> <br/> |<span data-ttu-id="eaf2c-124">int</span><span class="sxs-lookup"><span data-stu-id="eaf2c-124">int</span></span>  <br/> |<span data-ttu-id="eaf2c-125">Externes</span><span class="sxs-lookup"><span data-stu-id="eaf2c-125">Foreign</span></span>  <br/> |<span data-ttu-id="eaf2c-126">Numéro unique identifiant cet utilisateur, référencé dans la [table utilisateurs](users.md).</span><span class="sxs-lookup"><span data-stu-id="eaf2c-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="eaf2c-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="eaf2c-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="eaf2c-128">type</span><span class="sxs-lookup"><span data-stu-id="eaf2c-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="eaf2c-129">Nombre de messages envoyés par cet utilisateur au cours de cette conférence.</span><span class="sxs-lookup"><span data-stu-id="eaf2c-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

