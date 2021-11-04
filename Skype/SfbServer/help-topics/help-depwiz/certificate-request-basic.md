---
title: Demande de certificat (élémentaire)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: La page Nom et sécurité Paramètres fournit une zone de texte qui permet de définir un nom convivial, une liste de listes de texte pour la longueur de bits de la paire de clés privées et publiques et une case à cocher qui vous permet de marquer la clé privée du certificat comme exportable.
ms.openlocfilehash: 445a71c4655a8325de85165f1970b85fc536dff9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764272"
---
# <a name="certificate-request-basic"></a>Demande de certificat (élémentaire)
 
La page Nom et sécurité **Paramètres** fournit une zone de texte pour définir un nom **convivial,** une liste de listes listes pour la longueur de **bits** de la paire de clés privées et publiques, et une case à cocher qui vous permet de marquer la clé privée du certificat comme **exportable.**
  
Le nom convivial sur un certificat est un nom facilement reconnaissable qui permet à la personne qui consulte le certificat de l’identifier plus facilement.
  
La longueur en bits de la paire de clés privée et publique peut être 1024, 2048 ou 4096.
  
Si vous cochez la case Pour marquer la clé privée du certificat comme **exportable,** le certificat et la clé privée peuvent être exportés et déplacés vers un autre ordinateur ou serveur. La seule fois que cela est nécessaire, c’est lorsque vous créez un pool de serveurs Edge pour le service d’authentification de relais multimédia (MRAS).
  
> [!CAUTION]
> Pour maintenir la sécurité du certificat et de la paire de clés, vous devez sélectionner l’option Marquer la clé privée du certificat comme exportable uniquement si cela est absolument nécessaire. 
  

