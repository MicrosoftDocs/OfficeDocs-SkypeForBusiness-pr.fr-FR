---
title: Domaines approuvés de Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.
ms.openlocfilehash: 618ea5ce6cd4e12cd1e6a811a065f7a29a5c9ced
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768667"
---
# <a name="skype-room-system-trusted-domains"></a>Domaines approuvés de Skype Room System
 
Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.
  
## <a name="trusted-domains"></a>Domaines approuvés

Le client Skype entreprise affiche une boîte de dialogue permettant aux utilisateurs d’accepter le certificat du serveur Skype entreprise si le domaine SIP du compte d’utilisateur qui se connecte est différent du nom figurant dans le nom de l’objet ou de l’objet du certificat. Si le certificat configuré pour Skype entreprise Server au sein de votre organisation n’a pas de nom de domaine SIP pour le compte système de salle Skype pour le nom de domaine de l’objet ou du sujet, vous devez configurer les domaines présentés sur le certificat sous domaines approuvés. clé de Registre sur la machine de la console du système de salle Skype. Le Guide de l’administrateur système de salle Skype fourni par le fabricant vous explique comment et où ajouter des domaines approuvés dans le client Skype entreprise. 
  
Par exemple, supposons que les certificats configurés sur Skype entreprise Server possèdent le nom d’objet/de l’objet « CONTOSO ». LOCALE» et l’un des domaines SIP attribués à un utilisateur pour l’adresse de connexion de votre système de salle Skype est « confrm1@contoso.net ». Dans la mesure où contoso.net ne figure pas dans le certificat, vous devez configurer « contoso. local » en tant que domaine approuvé dans le registre, comme indiqué dans le Guide de l’administrateur de votre système de salle Skype. 
  

