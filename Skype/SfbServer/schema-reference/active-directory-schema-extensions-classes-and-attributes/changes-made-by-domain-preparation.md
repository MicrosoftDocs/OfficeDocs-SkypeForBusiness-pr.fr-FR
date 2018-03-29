---
title: Modifications apportées par la préparation du domaine dans Skype pour Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: Le tableau suivant répertorie les entrées de contrôle d’accès (ACE) qui crée de préparation du domaine sur la racine du domaine. Toutes les ACE sont héritées, sauf indication contraire.
ms.openlocfilehash: 3602e04082dbf4af9a2ab40fc3318761ebc08c21
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Modifications apportées par la préparation du domaine dans Skype pour Business Server
 
Le tableau suivant répertorie les entrées de contrôle d’accès (ACE) qui crée de préparation du domaine sur la racine du domaine. Toutes les ACE sont héritées, sauf indication contraire.
  
**Entrées ajoutées à la racine du domaine**

|**ACE**|**Groupe-UserReadOnly-RTCUniversal**|**Groupe-ServerReadOnly-RTCUniversal**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Services**|**Utilisateurs authentifiés**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Conteneur de lecture (non hérité)  <br/> |**Oui** <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lecture utilisateur PropertySet-compte-Restrictions utilisateur  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lecture utilisateur PropertySet-informations personnelles  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lire PropertySet général-informations utilisateur  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lecture des informations utilisateur PropertySet publiques  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lecture utilisateur PropertySet RTCUserSearchProperty-jeu  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |
|Lecture utilisateur PropertySet RTCPropertySet  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Écrire adresses Proxy de propriété utilisateur  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |
|Écrire l’utilisateur PropertySet RTCUserSearchProperty-jeu  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |
|Écrire l’utilisateur PropertySet RTCPropertySet  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |
|Lecture PropertySet DS-réplication-Get-modifications de tous les objets Active Directory  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |
   
Le tableau suivant répertorie les ACE qui crée de préparation du domaine dans les trois conteneurs intégrés : les utilisateurs, les ordinateurs et les contrôleurs de domaine. Toutes les ACE sont héritées, sauf indication contraire.
**Entrées ajoutées aux conteneurs intégrés**

|**ACE**|**Groupe-UserReadOnly-RTCUniversal**|**Groupe-ServerReadOnly-RTCUniversal**|
|:-----|:-----|:-----|
|Conteneur de lecture (non hérité)  <br/> |**Oui** <br/> |**Oui** <br/> |
   

