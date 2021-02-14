---
title: Table ContentTypes dans Skype Entreprise Server 2015
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
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La table ContentTypes est une table annexe qui stocke la liste des types de contenu utilisés dans les sessions d’égal à égal et dans les sessions de conférence. Chaque enregistrement de la table représente un type de contenu.
ms.openlocfilehash: 461631c8fc824a23f0e4b22b65a3cbc8cf6a2c73
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816084"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e7952-104">Table ContentTypes dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e7952-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e7952-p102">La table ContentTypes est une table annexe qui stocke la liste des types de contenu utilisés dans les sessions d’égal à égal et dans les sessions de conférence. Chaque enregistrement de la table représente un type de contenu.</span><span class="sxs-lookup"><span data-stu-id="e7952-p102">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions. Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="e7952-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e7952-107">**Column**</span></span>|<span data-ttu-id="e7952-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e7952-108">**Data Type**</span></span>|<span data-ttu-id="e7952-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="e7952-109">**Key/Index**</span></span>|<span data-ttu-id="e7952-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e7952-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e7952-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="e7952-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="e7952-112">int</span><span class="sxs-lookup"><span data-stu-id="e7952-112">int</span></span>  <br/> |<span data-ttu-id="e7952-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="e7952-113">Primary</span></span>  <br/> |<span data-ttu-id="e7952-114">Numéro unique d’identification du type de contenu.</span><span class="sxs-lookup"><span data-stu-id="e7952-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="e7952-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="e7952-115">**ContentType**</span></span> <br/> |<span data-ttu-id="e7952-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e7952-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="e7952-117">Nom du type de contenu.</span><span class="sxs-lookup"><span data-stu-id="e7952-117">Content type name.</span></span>  <br/> |
   

