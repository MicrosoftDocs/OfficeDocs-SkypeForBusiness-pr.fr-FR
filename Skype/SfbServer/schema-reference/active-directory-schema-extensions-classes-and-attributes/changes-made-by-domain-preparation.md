---
title: Modifications apportées par la préparation du domaine dans Skype pour Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: Le tableau suivant répertorie les entrées de contrôle d’accès (ACE) par la préparation du domaine sur le domaine racine. Toutes les ACE sont héritées, sauf indication contraire.
ms.openlocfilehash: 5cf239e37badafee9980140d08fd20a11e3c233d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877698"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Modifications apportées par la préparation du domaine dans Skype pour Business Server
 
Le tableau suivant répertorie les entrées de contrôle d’accès (ACE) par la préparation du domaine sur le domaine racine. Toutes les ACE sont héritées, sauf indication contraire.
  
**ACE ajoutées à la racine du domaine**

|**ACE**|**Groupe-UserReadOnly-RTCUniversal**|**Groupe-ServerReadOnly-RTCUniversal**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Services**|**Utilisateurs authentifiés**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Lire le conteneur (non héritée)  <br/> |**Oui** <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lecture utilisateur utilisateur PropertySet Restrictions de compte  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lire les informations utilisateur PropertySet personnel  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lisez les informations utilisateur PropertySet générales  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lisez les informations utilisateur PropertySet publiques  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lire PropertySet RTCUserSearchProperty-ensemble d’utilisateurs  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |
|Lecture utilisateur PropertySet RTCPropertySet  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Écrire des adresses Proxy de propriété utilisateur  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |
|Écrire PropertySet RTCUserSearchProperty-ensemble d’utilisateurs  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |
|Écriture utilisateur PropertySet RTCPropertySet  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |
|Read PropertySet DS-Replication-Get-Changes de tous les objets Active Directory  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |
   
Le tableau suivant répertorie les ACE par la préparation de domaine dans les trois conteneurs intégrés : utilisateurs, ordinateurs et contrôleurs de domaine. Toutes les ACE sont héritées, sauf indication contraire.
**ACE ajoutées aux conteneurs intégrés**

|**ACE**|**Groupe-UserReadOnly-RTCUniversal**|**Groupe-ServerReadOnly-RTCUniversal**|
|:-----|:-----|:-----|
|Lire le conteneur (non héritée)  <br/> |**Oui** <br/> |**Oui** <br/> |
   

