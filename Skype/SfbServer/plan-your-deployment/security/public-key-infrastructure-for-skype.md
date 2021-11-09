---
title: Infrastructure à clé publique pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype Entreprise Server s’appuie sur des certificats pour l’authentification du serveur et pour établir une chaîne de confiance entre les clients et les serveurs et entre les différents rôles serveur. L’infrastructure à clé publique (PKI) Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 et Windows Server 2008 fournit l’infrastructure pour établir et valider cette chaîne d’confiance.
ms.openlocfilehash: 61381840d6c82ce26f0b8e7e5210ebd37c3532c0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840956"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Infrastructure à clé publique pour Skype Entreprise Server
 
Skype Entreprise Server s’appuie sur des certificats pour l’authentification du serveur et pour établir une chaîne de confiance entre les clients et les serveurs et entre les différents rôles serveur. L’infrastructure à clé publique (PKI) Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 et Windows Server 2008 fournit l’infrastructure pour établir et valider cette chaîne d’confiance.
  
Les certificats sont des identifiants numériques. Ils identifient un serveur à l’aide de son nom et spécifient ses propriétés. Pour s’assurer que les informations d’un certificat sont valides, le certificat doit être émis par une cae qui est fiable par les clients ou d’autres serveurs qui se connectent au serveur. Si le serveur se connecte uniquement à d’autres clients et serveurs sur un réseau privé, l’autorité de certification peut être une autorité de certification d’entreprise. Si le serveur communique avec des entités en dehors du réseau privé, une autorité de certification publique peut être nécessaire.
  
Même si les informations du certificat sont valides, il doit être possible de vérifier si le serveur soumettant le certificat est réellement celui qu’il représente. C’est à ce niveau qu’intervient l’infrastructure à clé publique Windows.
  
Chaque certificat est lié à une clé publique. Le serveur nommé dans le certificat détient une clé privée correspondante qu’il est le seul à connaître. Lorsqu’un client ou un serveur se connecte, il utilise la clé publique pour chiffrer une information aléatoire qu’il envoie au serveur. Si le serveur déchiffre les informations et les renvoie sous forme de texte simple, l’entité connectée est sûre que le serveur détient la clé privée du certificat et qu’il s’agit donc bien du serveur nommé dans le certificat.
  
> [!NOTE]
> Toutes les CAs publiques ne sont pas conformes aux exigences de Skype Entreprise Server certificats. Nous vous recommandons de vous reporter à la liste des fournisseurs d’autorités de certification publiques certifiées selon vos besoins de certificats publics. 
  
## <a name="crl-distribution-points"></a>Points de distribution de liste de révocation de certificats (CRL)

Skype Entreprise Server tous les certificats de serveur doivent contenir un ou plusieurs points de distribution de liste de révocation de certificats (CRL). Il s’agit d’emplacements à partir desquels il est possible de télécharger des listes de révocation de certificats afin de vérifier si un certificat a été révoqué depuis son émission et s’il est toujours dans sa période de validité. Un point de distribution de liste de révocation de certificats figure dans les propriétés du certificat sous forme d’URL, généralement HTTP sécurisée.
  
## <a name="enhanced-key-usage"></a>Utilisation améliorée de la clé

Skype Entreprise Server tous les certificats de serveur doivent prendre en charge l’utilisation améliorée de la clé (EKU) dans le but de l’authentification du serveur. La configuration du champ EKU pour l’authentification de serveurs signifie que le certificat est valide pour l’authentification des serveurs. L’utilisation améliorée de la clé est essentielle pour MTLS. Le champ EKU peut contenir plusieurs entrées, ce qui permet d’activer le certificat à plusieurs fins.
  

