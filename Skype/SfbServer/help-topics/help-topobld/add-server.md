---
title: Ajouter un serveur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Pour ajouter un nouveau serveur à un pool de serveurs existant, où le pool est l’un des éléments suivants:'
ms.openlocfilehash: 32033d7d758528fc925c5c228971c040828bd654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290505"
---
# <a name="add-server"></a>Ajouter un serveur
 
Pour ajouter un nouveau serveur à un pool de serveurs existant, où le pool est l’un des éléments suivants:
  
- Serveur frontal d’Enterprise Edition
    
- Serveur Director
    
- serveur de médiation
    
- Serveur de visioconférence audio/vidéo
    
- Serveur d’applications de confiance
    
Chacun des nouveaux serveurs de pools a des exigences différentes. Dans les sections suivantes, recherchez le type de serveur que vous ajoutez au pool existant, puis fournissez les informations demandées comme il est défini pour chaque type de serveur. Vous fournissez les informations demandées pour définir le nouveau serveur du pool.
  
 **Serveur frontal d’Enterprise Edition**
  
- Nom de domaine complet (FQDN) du nouveau serveur, tel qu’il est défini dans DNS (Domain Name System).
    
- Sélectionnez **utiliser toutes les adresses IP configurées**, ce qui signifie que toute adresse IP définie sur l’ordinateur peut être utilisée. Vous pouvez également sélectionner **limiter l’utilisation du service aux adresses IP sélectionnées** et entrer une adresse particulière sur le nouveau serveur. L’adresse IP entrée est la seule adresse IP qui répond aux services hébergés.
    
- Définissez une **adresse IP RTC** quand un serveur de médiation est colocalisé sur le serveur frontal.
    
- Sélectionnez **activer IPv6** pour activer le protocole IPv6 pour ce serveur.
    
  **Serveur Director**
  
- Nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.
    
- Activez l’option **utiliser toutes les adresses IP configurées**, ce qui signifie que toute adresse IP définie sur l’ordinateur sera utilisée. Vous pouvez également sélectionner **limiter l’utilisation du service aux adresses IP sélectionnées** et entrer une adresse IP particulière sur le nouveau serveur. L’adresse IP entrée est la seule adresse IP qui répond aux services hébergés.
    
  **Serveur de médiation**
  
- Nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.
    
- Sélectionnez **utiliser toutes les adresses IP configurées**, ce qui signifie que toute adresse IP définie sur l’ordinateur peut être utilisée. Vous pouvez également sélectionner **limiter l’utilisation du service aux adresses IP sélectionnées** et entrer une adresse IP particulière sur le nouveau serveur en tant qu’adresse IP principale et entrer une adresse IP pour l’adresse IP du réseau téléphonique public commuté (RTC). Les adresses IP entrées sont la seule adresse IP qui répond aux services désignés.
    
    > [!NOTE]
    > Pour le serveur de médiation, l’adresse IP entrée pour l’adresse IP principale et l’adresse IP RTC est identique par défaut. Les adresses IP peuvent être définies séparément si vous utilisez des interfaces réseau dédiées ou des adresses IP distinctes sur la même interface réseau. Si vous avez deux interfaces réseau, une pour la connexion réseau locale et une pour la connexion RTC, vous devez attribuer des adresses IP différentes. 
  
  **Serveur de visioconférence audio/vidéo**
  
- Nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.
    
- Sélectionnez **utiliser toutes les adresses IP configurées**, ce qui signifie que toute adresse IP définie sur l’ordinateur peut être utilisée. Vous pouvez également sélectionner **limiter l’utilisation du service aux adresses IP sélectionnées** et entrer une adresse particulière sur le nouveau serveur. L’adresse IP entrée est la seule adresse IP qui répond aux services hébergés.
    
  **Serveur d’applications de confiance**
  
- Nom de domaine complet du nouveau serveur tel qu’il est défini dans DNS.
    

