---
title: Demande de certificat (élémentaire)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: La page Nom et paramètres de sécurité fournit une zone de texte pour définir un nom convivial, une liste déroulante pour la longueur en bits de la paire de clés publique et privée et une case à cocher qui vous permet de marquer la clé du certificat privée comme étant exportable.
ms.openlocfilehash: e9c70074a168b00288b931cb168b5fea210367c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-request-basic"></a>Demande de certificat (élémentaire)
 
La page **nom et paramètres de sécurité** fournit une zone de texte pour définir un **Nom convivial**, une liste déroulante pour la **longueur en bits** de la paire de clés publique et privée et une case à cocher qui vous permet de **marque le certificat de clé privée en tant que exportable**.
  
Le nom convivial sur un certificat est un nom facilement reconnaissable qui permet à la personne qui consulte le certificat de l’identifier plus facilement.
  
La longueur en bits de la paire de clés privée et publique peut être 1024, 2048 ou 4096.
  
Sélection de la case à cocher pour **Marquer la clé du certificat privée comme étant exportable** permet le certificat et la clé privée à être exportée et déplacée vers un autre ordinateur ou serveur. Le seul cas où cela est nécessaire est quand vous créez un pool de serveurs Edge pour le service d’authentification du serveur relais multimédia.
  
> [!CAUTION]
> Pour vous aider à maintenir la sécurité du certificat et la paire de clés, vous devez sélectionner la marque de la clé du certificat privé comme option d’exportation uniquement si cela est absolument nécessaire. 
  

