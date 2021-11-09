---
title: Demande de certificat (élémentaire)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
description: La page Nom et sécurité Paramètres fournit une zone de texte pour définir un nom convivial, une liste de listes listes pour la longueur de bits de la paire de clés privées et publiques et une case à cocher qui vous permet de marquer la clé privée du certificat comme exportable.
ms.openlocfilehash: dcb26b7ffe310b593d5e73e6602551c98cf1eb2d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865001"
---
# <a name="certificate-request-basic"></a>Demande de certificat (élémentaire)
 
La page Nom et sécurité **Paramètres** fournit une zone de texte pour définir un nom **convivial,** une liste de listes listes pour la longueur de **bits** de la paire de clés privées et publiques, et une case à cocher qui vous permet de marquer la clé privée du certificat comme **exportable.**
  
Le nom convivial sur un certificat est un nom facilement reconnaissable qui permet à la personne qui consulte le certificat de l’identifier plus facilement.
  
La longueur en bits de la paire de clés privée et publique peut être 1024, 2048 ou 4096.
  
Si vous cochez la case Pour marquer la clé privée du certificat comme **exportable,** le certificat et la clé privée peuvent être exportés et déplacés vers un autre ordinateur ou serveur. La seule fois que cela est nécessaire, c’est lorsque vous créez un pool de serveurs Edge pour le service d’authentification de relais multimédia (MRAS).
  
> [!CAUTION]
> Pour maintenir la sécurité du certificat et de la paire de clés, vous devez sélectionner l’option Marquer la clé privée du certificat comme exportable uniquement si cela est absolument nécessaire. 
  

