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
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Table ConferenceMessageCount dans Skype entreprise Server 2015
 
Chaque enregistrement de cette table représente un utilisateur au sein d’une conférence par messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur. Chaque conférence est représentée par plusieurs enregistrements dans ce tableau ; un enregistrement pour chaque utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Etranger principal  <br/> |Durée de l’instance de conférence. Utilisé conjointement avec **SessionIdSeq** pour identifier de manière unique une instance de conférence. Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Etranger principal  <br/> |Numéro d’identification pour identifier l’instance de conférence. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une instance de conférence. Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) . <br/> |
|**UserId** <br/> |int  <br/> |Externes  <br/> |Numéro unique identifiant cet utilisateur, référencé dans la [table utilisateurs](users.md).  <br/> |
|**MessageCount** <br/> |type  <br/> | <br/> |Nombre de messages envoyés par cet utilisateur au cours de cette conférence.  <br/> |
   

