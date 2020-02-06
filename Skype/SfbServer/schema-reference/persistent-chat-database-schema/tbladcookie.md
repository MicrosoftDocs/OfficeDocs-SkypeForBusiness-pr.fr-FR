---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actuels.
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814702"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actuels.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, pas null  <br/> |GUID principal du domaine qui est surveillé.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Nom de domaine complet (FQDN) du contrôleur de domaine actuel utilisé pour la synchronisation des services de domaine Active Directory (AD DS). A une valeur d’information.  <br/> |
|adcContent  <br/> |image (binaire)  <br/> |Cookie de synchronisation Active Directory.  <br/> |
|lastUpdated  <br/> |DateHeure  <br/> |Date et heure de la mise à jour de ligne.  <br/> |
|lockedUntil  <br/> |DateHeure  <br/> |Temps nécessaire au verrouillage de la ligne pour les modifications. Il s’agit d’une partie d’un mécanisme de verrouillage de logiciels qui garantit que seul l’un des services de chat effectue la synchronisation Active Directory à la fois.  <br/> |
   
**Permettent**

|**Colonne (s)**|**Description**|
|:-----|:-----|
|prinGuid  <br/> |Clé primaire.  <br/> |
|prinGuid  <br/> |Clé étrangère avec recherche dans la table principale. prinGuid.  <br/> |
   

