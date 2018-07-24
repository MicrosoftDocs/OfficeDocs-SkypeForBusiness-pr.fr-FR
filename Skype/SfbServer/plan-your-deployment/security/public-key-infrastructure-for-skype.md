---
title: Infrastructure à clé publique pour Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype pour Business Server repose sur les certificats pour l’authentification de serveur et d’établir une chaîne d’approbation entre les clients et serveurs et entre les différents rôles de serveur. Le Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 et Windows Server 2008 Public Key Infrastructure (PKI) fournit l’infrastructure pour établir et de valider cette chaîne d’approbation.
ms.openlocfilehash: 7430ccfd9c5eacac3e5deef845b7eafb83275500
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974255"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Infrastructure à clé publique pour Skype pour Business Server
 
Skype pour Business Server repose sur les certificats pour l’authentification de serveur et d’établir une chaîne d’approbation entre les clients et serveurs et entre les différents rôles de serveur. Le Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 et Windows Server 2008 Public Key Infrastructure (PKI) fournit l’infrastructure pour établir et de valider cette chaîne d’approbation.
  
Les certificats sont des ID numériques. Ils identifient un serveur par son nom et indiquent ses propriétés. Afin de garantir que les informations d’un certificat sont valides, celui-ci doit être émis par une autorité de certification (CA) approuvée par les clients ou d’autres serveurs qui se connectent au serveur. Si le serveur se connecte uniquement avec d’autres clients et serveurs sur un réseau privé, la CA peut être une CA d’entreprise. Si le serveur interagit avec des entités en dehors du réseau privé, une CA publique peut être requise.
  
Même si les informations du certificat sont valides, il doit exister un moyen de vérifier que le serveur présentant le certificat est en fait celui représenté par le certificat. C’est ici que le PKI de Windows entre en jeu.
  
Chaque certificat est lié à une clé publique. Le serveur nommé sur le certificat contient une clé privée correspondante que lui seul connaît. Un client ou serveur se connectant utilise la clé publique pour chiffrer une information aléatoire et l’envoie au serveur. Si le serveur déchiffre l’information et la retourne sous forme de texte simple, l’entité se connectant peut ainsi être sûre que le serveur contient la clé privée du certificat et qu’il s’agit donc du serveur nommé sur le certificat.
  
> [!NOTE]
> Pas de toutes les autorités de certification publiques respectent les exigences de Skype pour les certificats de serveur d’entreprise. Nous vous conseillons de vous reporter à la liste des autorités de certification publiques approuvées pour vos besoins de certificats publics. Pour plus d’informations, voir [Partenaires de certificat de Communications unifiées](https://go.microsoft.com/fwlink/p/?LinkId=140898). 
  
## <a name="crl-distribution-points"></a>Points de distribution de liste de révocation de certificats

Skype pour Business Server requiert tous les certificats de serveur pour contenir un ou plusieurs points de distribution de liste de révocation de certificats (CRL). Les points de distribution CRL (CDP) sont des emplacements à partir desquels les CRL peuvent être téléchargés en vue de vérifier que le certificat n’a pas été révoqué depuis son émission et qu’il est toujours dans sa période de validité. Un point de distribution CRL est indiqué dans les propriétés du certificat sous forme d’URL et il s’agit généralement d’une adresse HTTP sécurisée.
  
## <a name="enhanced-key-usage"></a>Utilisation améliorée de la clé

Skype pour Business Server requiert tous les certificats de serveur pour prendre en charge d’utilisation avancée de la clé (EKU) pour les besoins de l’authentification de serveur. La configuration du champ EKU pour l’authentification du serveur signifie que le certificat est valide pour l’authentification des serveurs. Cette EKU est essentielle pour MTLS. Il est possible d’avoir plusieurs entrées dans l’EKU, ce qui permet au certificat d’avoir plusieurs rôles.
  

