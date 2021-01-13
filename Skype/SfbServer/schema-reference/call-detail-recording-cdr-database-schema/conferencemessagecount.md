---
title: Table ConferenceMessageCount dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Chaque enregistrement de ce tableau représente un utilisateur dans une conférence de messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur. Chaque conférence est représentée par plusieurs enregistrements dans cette table ; un enregistrement pour chaque utilisateur.
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813274"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2a625-104">Table ConferenceMessageCount dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="2a625-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2a625-105">Chaque enregistrement de ce tableau représente un utilisateur dans une conférence de messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a625-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="2a625-106">Chaque conférence est représentée par plusieurs enregistrements dans cette table ; un enregistrement pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a625-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="2a625-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2a625-107">**Column**</span></span>|<span data-ttu-id="2a625-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="2a625-108">**Data Type**</span></span>|<span data-ttu-id="2a625-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="2a625-109">**Key/Index**</span></span>|<span data-ttu-id="2a625-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="2a625-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a625-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="2a625-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="2a625-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2a625-112">datetime</span></span>  <br/> |<span data-ttu-id="2a625-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="2a625-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2a625-114">Heure de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="2a625-114">Time of conference instance.</span></span> <span data-ttu-id="2a625-115">Utilisé conjointement avec **SessionIdSeq** pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="2a625-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="2a625-116">Pour plus d’informations, voir le tableau Conférences dans Skype Entreprise [Server 2015.](conferences.md)</span><span class="sxs-lookup"><span data-stu-id="2a625-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2a625-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="2a625-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="2a625-118">int</span><span class="sxs-lookup"><span data-stu-id="2a625-118">int</span></span>  <br/> |<span data-ttu-id="2a625-119">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="2a625-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2a625-120">Numéro d’identification de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="2a625-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="2a625-121">Utilisé conjointement avec **SessionIdTime pour** identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="2a625-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="2a625-122">Pour plus d’informations, voir le tableau Conférences dans Skype Entreprise [Server 2015.](conferences.md)</span><span class="sxs-lookup"><span data-stu-id="2a625-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2a625-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="2a625-123">**UserId**</span></span> <br/> |<span data-ttu-id="2a625-124">int</span><span class="sxs-lookup"><span data-stu-id="2a625-124">int</span></span>  <br/> |<span data-ttu-id="2a625-125">Étranger</span><span class="sxs-lookup"><span data-stu-id="2a625-125">Foreign</span></span>  <br/> |<span data-ttu-id="2a625-126">Numéro unique identifiant cet utilisateur, référencé à partir de la [table Utilisateurs](users.md).</span><span class="sxs-lookup"><span data-stu-id="2a625-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="2a625-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="2a625-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="2a625-128">smallint</span><span class="sxs-lookup"><span data-stu-id="2a625-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="2a625-129">Nombre de messages envoyés par cet utilisateur au cours de cette conférence.</span><span class="sxs-lookup"><span data-stu-id="2a625-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

