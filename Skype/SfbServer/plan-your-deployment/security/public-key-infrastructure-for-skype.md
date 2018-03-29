---
title: Infrastructure à clé publique pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype pour Business Server 2015 s’appuie sur les certificats pour l’authentification du serveur et établir une chaîne de confiance entre clients et serveurs et entre les différents rôles de serveur. Le Windows Server 2012 R2 Windows Server 2012, Windows Server 2008 R2 et Windows Server 2008 Public Key Infrastructure (PKI) fournit l’infrastructure pour l’établissement et la validation de cette chaîne de confiance.
ms.openlocfilehash: 8987eb0919f7fd7dcebb98211cebb9814e93771b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="public-key-infrastructure-for-skype-for-business-server-2015"></a>Infrastructure à clé publique pour Skype Entreprise Server 2015
 
Skype pour Business Server 2015 s’appuie sur les certificats pour l’authentification du serveur et établir une chaîne de confiance entre clients et serveurs et entre les différents rôles de serveur. Le Windows Server 2012 R2 Windows Server 2012, Windows Server 2008 R2 et Windows Server 2008 Public Key Infrastructure (PKI) fournit l’infrastructure pour l’établissement et la validation de cette chaîne de confiance.
  
Les certificats sont des ID numériques. Ils identifient un serveur par son nom et indiquent ses propriétés. Afin de garantir que les informations d’un certificat sont valides, celui-ci doit être émis par une autorité de certification (CA) approuvée par les clients ou d’autres serveurs qui se connectent au serveur. Si le serveur se connecte uniquement avec d’autres clients et serveurs sur un réseau privé, la CA peut être une CA d’entreprise. Si le serveur interagit avec des entités en dehors du réseau privé, une CA publique peut être requise.
  
Même si les informations du certificat sont valides, il doit exister un moyen de vérifier que le serveur présentant le certificat est en fait celui représenté par le certificat. C’est ici que le PKI de Windows entre en jeu.
  
Chaque certificat est lié à une clé publique. Le serveur nommé sur le certificat contient une clé privée correspondante que lui seul connaît. Un client ou serveur se connectant utilise la clé publique pour chiffrer une information aléatoire et l’envoie au serveur. Si le serveur déchiffre l’information et la retourne sous forme de texte simple, l’entité se connectant peut ainsi être sûre que le serveur contient la clé privée du certificat et qu’il s’agit donc du serveur nommé sur le certificat.
  
> [!NOTE]
> Pas de toutes les autorités de certification publiques conformes aux exigences de Skype pour les certificats de Business Server 2015. Nous vous conseillons de vous reporter à la liste des autorités de certification publiques approuvées pour vos besoins de certificats publics. Pour plus d’informations, reportez-vous à la section [Partenaires de certificat de Communications unifiées](https://go.microsoft.com/fwlink/p/?LinkId=140898). 
  
## <a name="crl-distribution-points"></a>Points de distribution de liste de révocation de certificats

Skype pour Business Server 2015 nécessite tous les certificats de serveur pour contenir un ou plusieurs points de distribution de liste de révocation de certificats (CRL). Les points de distribution CRL (CDP) sont des emplacements à partir desquels les CRL peuvent être téléchargés en vue de vérifier que le certificat n’a pas été révoqué depuis son émission et qu’il est toujours dans sa période de validité. Un point de distribution CRL est indiqué dans les propriétés du certificat sous forme d’URL et il s’agit généralement d’une adresse HTTP sécurisée.
  
## <a name="enhanced-key-usage"></a>Utilisation améliorée de la clé

Skype pour Business Server 2015 nécessite tous les certificats de serveur pour prendre en charge l’utilisation de clé améliorée (EKU) pour l’authentification du serveur. La configuration du champ EKU pour l’authentification du serveur signifie que le certificat est valide pour l’authentification des serveurs. Cette EKU est essentielle pour MTLS. Il est possible d’avoir plusieurs entrées dans l’EKU, ce qui permet au certificat d’avoir plusieurs rôles.
  

