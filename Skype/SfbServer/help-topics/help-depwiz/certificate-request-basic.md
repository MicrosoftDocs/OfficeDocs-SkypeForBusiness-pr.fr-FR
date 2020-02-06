---
title: Demande de certificat (élémentaire)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: La page Paramètres de nom et de sécurité fournit une zone de texte pour définir un nom convivial, une liste déroulante pour la longueur de bits de la paire de clés privée et publique et une case à cocher vous permettant de marquer la clé privée du certificat comme étant exportable.
ms.openlocfilehash: 182edc086863b7fb2ffbbb67cc041434fa9df672
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823908"
---
# <a name="certificate-request-basic"></a>Demande de certificat (élémentaire)
 
La page **paramètres de nom et de sécurité** fournit une zone de texte pour définir un **nom convivial**, une liste déroulante pour la **longueur de bits** de la paire de clés privée et publique et une case à cocher vous permettant de **marquer la clé privée du certificat comme étant exportable**.
  
Le nom convivial sur un certificat est un nom facilement reconnaissable qui permet à la personne qui consulte le certificat de l’identifier plus facilement.
  
La longueur en bits de la paire de clés privée et publique peut être 1024, 2048 ou 4096.
  
L’activation de la case à cocher **marquer la clé privée du certificat comme étant exportable** permet d’exporter et de déplacer le certificat et la clé privée vers un autre ordinateur ou serveur. Le seul cas où cela est nécessaire est quand vous créez un pool de serveurs Edge pour le service d’authentification du serveur relais multimédia.
  
> [!CAUTION]
> Pour garantir la sécurité du certificat et de la paire de clés, vous devez sélectionner l’option marquer la clé privée du certificat comme étant exportable uniquement si elle est absolument nécessaire. 
  

