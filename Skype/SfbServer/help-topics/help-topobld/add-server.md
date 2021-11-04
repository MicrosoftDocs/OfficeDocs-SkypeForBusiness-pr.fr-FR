---
title: Ajouter un serveur
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Pour ajouter un nouveau serveur à un pool de serveurs existant, où le pool est l’un des suivants :'
ms.openlocfilehash: 04a6412419ba9828dbb4dea70fcd4b30604c2213
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772280"
---
# <a name="add-server"></a>Ajouter un serveur
 
Pour ajouter un nouveau serveur à un pool de serveurs existant, où le pool est l’un des suivants :
  
- Serveur frontal Enterprise Edition
    
- Serveur directeur
    
- Serveur de médiation
    
- Serveur de conférence audio/vidéo
    
- Serveur d’applications approuvées
    
Chaque nouveau serveur de pool a des exigences différentes. Dans les sections suivantes, recherchez le type de serveur que vous ajoutez à un pool existant et fournissez les informations requises tel que définit pour chaque type de serveur. Fournissez les informations demandées pour définir le nouveau pool de serveurs.
  
 **Serveur frontal Enterprise Edition**
  
- Le nom de domaine complet (FQDN) du nouveau serveur tel qu’il est défini dans DNS (Domain Name System).
    
- Sélectionnez **Utiliser toutes les adresses IP configurées**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée. Vous pouvez également sélectionner **Limiter l’utilisation des services aux adresses spécifiées** et entrer une adresse spécifique sur le nouveau serveur. L’adresse IP entrée est la seule adresse IP qui répondra aux services hébergés.
    
- Définissez une **Adresse IP PSTN** lorsqu’un serveur de médiation est colocalisé sur le serveur frontal.
    
- Sélectionnez **Activer IPv6** pour activer IPv6 pour ce serveur.
    
  **Serveur directeur**
  
- Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.
    
- Sélectionnez **Utiliser toutes les adresses IP configurées**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur sera utilisée. Vous pouvez aussi sélectionner **Limiter l’utilisation des services aux adresses IP sélectionnées** et entrer une adresse IP spécifique sur le nouveau serveur. L’adresse IP entrée est la seule adresse IP qui répondra aux services hébergés.
    
  **Serveur de médiation**
  
- Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.
    
- Sélectionnez **Utiliser toutes les adresses IP configurées**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée. Vous pouvez également sélectionner **Limiter l’utilisation des services aux adresses IP sélectionnées** et entrer une adresse IP spécifique sur le nouveau serveur en tant qu’adresse IP primaire, et une adresse IP pour l'adresse IP du réseau téléphonique commuté (PSTN). Les adresses IP entrées sont les seules adresses IP qui répondront aux services désignés.
    
    > [!NOTE]
    > Pour le serveur de médiation, l’adresse IP entrée pour l’adresse IP principale et l’adresse IP PSTN est identique par défaut. Les adresses IP peuvent être définies séparément si vous utilisez des interfaces réseau dédiées ou des adresses IP distinctes sur la même interface réseau. Si vous avez deux interfaces réseau, une pour la connexion au réseau local et une pour la connexion PSTN, vous devez assigner des adresses IP différentes. 
  
  **Serveur de conférence audio/vidéo**
  
- Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.
    
- Sélectionnez **Utiliser toutes les adresses IP configurées**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée. Vous pouvez également sélectionner **Limiter l’utilisation des services aux adresses spécifiées** et entrer une adresse spécifique sur le nouveau serveur. L’adresse IP entrée est la seule adresse IP qui répondra aux services hébergés.
    
  **Serveur d’applications approuvées**
  
- Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.
    

