---
title: Ajouter serveur
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Pour ajouter un nouveau serveur à un pool de serveurs, où le pool est une des opérations suivantes :'
ms.openlocfilehash: 609fbb28900ac67e0a4e1e2a400f1eebb29b2ff2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-server"></a>Ajouter serveur
 
Pour ajouter un nouveau serveur à un pool de serveurs, où le pool est une des opérations suivantes :
  
- Enterprise Edition Server frontal
    
- Serveur de directeur
    
- Serveur de médiation
    
- Serveur de conférence audio/vidéo
    
- Serveur d’applications de confiance
    
Chacun des nouveaux serveurs de pool a des besoins différents. Dans les sections suivantes, recherchez le type de serveur que vous ajoutez à la liste existante et fournir les renseignements demandés telle qu’elle est définie pour chaque type de serveur. Vous fournissez les informations requises pour définir le nouveau serveur du pool.
  
 **Enterprise Edition Server frontal**
  
- Nom de domaine (FQDN) du nouveau serveur complet tel qu’il est défini dans le système DNS (Domain Name System).
    
- Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisé. Sinon, vous pouvez sélectionnez **limiter l’utilisation de service aux adresses IP sélectionnées** et entrez une adresse spécifique sur le nouveau serveur. L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.
    
- Définissez une **adresse IP de RTPC** lorsqu’un serveur de médiation se trouve sur le serveur frontal.
    
- Sélectionnez **Activer l’IPv6** pour activer IPv6 pour ce serveur.
    
 **Serveur de directeur**
  
- Le nom de domaine complet du nouveau serveur tel qu’il est défini dans le système DNS.
    
- Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur sera utilisé. Vous pouvez également vous sélectionnez **limiter l’utilisation de service aux adresses IP sélectionnées** et entrez une adresse IP spécifique sur le nouveau serveur. L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.
    
 **Serveur de médiation**
  
- Le nom de domaine complet du nouveau serveur tel qu’il est défini dans le système DNS.
    
- Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisé. Vous pouvez également vous sélectionnez **limiter l’utilisation de service aux adresses IP sélectionnées** et entrer une adresse IP spécifique sur le nouveau serveur en tant que l’adresse IP principale et une entrée une adresse IP pour l’adresse IP du réseau téléphonique public commuté. Les adresses IP entrées sont la seule adresse IP qui répondra pour les services désignés.
    
    > [!NOTE]
    > Le serveur de médiation, l’adresse IP entrée pour l’adresse IP principale et l’adresse IP de PSTN est celle par défaut. Les adresses IP peuvent être définies séparément si vous utilisez les interfaces de réseau dédié ou adresses IP distinctes sur la même interface de réseau. Si vous avez des interfaces réseau de deux, une pour la connexion au réseau local et l’autre pour la connexion TLS, vous devez affecter des adresses IP différentes. 
  
 **Serveur de conférence audio/vidéo**
  
- Le nom de domaine complet du nouveau serveur tel qu’il est défini dans le système DNS.
    
- Sélectionnez **utiliser toutes les adresses IP**, ce qui signifie que n’importe quelle adresse IP définie sur l’ordinateur peut être utilisé. Sinon, vous pouvez sélectionnez **limiter l’utilisation de service aux adresses IP sélectionnées** et entrez une adresse spécifique sur le nouveau serveur. L’adresse IP saisie est la seule adresse IP qui répondra pour les services hébergés.
    
 **Serveur d’applications de confiance**
  
- Le nom de domaine complet du nouveau serveur tel qu’il est défini dans le système DNS.
    

