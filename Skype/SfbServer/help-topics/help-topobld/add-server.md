---
title: Ajouter un serveur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Pour ajouter un nouveau serveur à un pool existant de serveurs, où le pool est une des opérations suivantes :'
ms.openlocfilehash: 4ec03d28f71dffbeaa4b06594bd634e80e522665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897323"
---
# <a name="add-server"></a>Ajouter un serveur
 
Pour ajouter un nouveau serveur à un pool existant de serveurs, où le pool est une des opérations suivantes :
  
- Enterprise Edition Server frontal
    
- Serveur directeur
    
- serveur de médiation
    
- Serveur de conférence audio/vidéo
    
- Serveur d’applications approuvées
    
Chacun des nouveaux serveurs de pool a des exigences différentes. Dans les sections suivantes, recherchez le type de serveur que vous ajoutez au pool existant et fournit les informations demandées telle qu’elle est définie pour chaque type de serveur. Vous fournir les informations demandées pour définir le nouveau serveur du pool.
  
 **Enterprise Edition Server frontal**
  
- Domaine nom complet (FQDN) du nouveau serveur tel qu’il est défini dans le système DNS (Domain Name System).
    
- Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée. Sinon, vous pouvez sélectionner **limiter l’utilisation de service pour les adresses IP sélectionnées** et entrez une adresse spécifique sur le nouveau serveur. L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.
    
- Définir une **adresse IP PSTN** lorsqu’un serveur de médiation est colocalisé sur le serveur frontal.
    
- Sélectionnez **Activer IPv6** pour activer IPv6 pour ce serveur.
    
  **Serveur directeur**
  
- Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.
    
- Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur est utilisé. Vous pouvez également vous sélectionnez **limiter l’utilisation de service pour les adresses IP sélectionnées** et entrez une adresse IP spécifique sur le nouveau serveur. L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.
    
  **Serveur de médiation**
  
- Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.
    
- Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée. Vous pouvez également vous sélectionnez **limiter l’utilisation de service pour les adresses IP sélectionnées** et entrez une adresse IP spécifique sur le nouveau serveur en tant que l’adresse IP principale et une adresse IP pour l’adresse IP du réseau téléphonique commuté public entrée. Les adresses IP entrées sont la seule adresse IP qui répondra pour les services désignés.
    
    > [!NOTE]
    > Le serveur de médiation, l’adresse IP entrée pour l’adresse IP principale et l’adresse IP PSTN est le même par défaut. Les adresses IP peuvent être définies séparément si vous utilisez les interfaces réseau dédié ou des adresses IP séparées sur la même interface réseau. Si vous avez des interfaces réseau deux, l’autre pour la connexion au réseau local et l’autre pour la connexion PSTN, vous devez assigner des adresses IP différentes. 
  
  **Serveur de conférence audio/vidéo**
  
- Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.
    
- Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisée. Sinon, vous pouvez sélectionner **limiter l’utilisation de service pour les adresses IP sélectionnées** et entrez une adresse spécifique sur le nouveau serveur. L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.
    
  **Serveur d’applications approuvées**
  
- Le nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.
    

