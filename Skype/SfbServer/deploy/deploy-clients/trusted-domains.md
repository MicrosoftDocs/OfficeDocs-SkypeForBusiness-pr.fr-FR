---
title: Domaines de confiance Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lisez cette rubrique pour découvrir comment configurer des domaines de confiance pour Skype Room System et Skype Entreprise.
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834114"
---
# <a name="skype-room-system-trusted-domains"></a>Domaines de confiance Skype Room System
 
Lisez cette rubrique pour découvrir comment configurer des domaines de confiance pour Skype Room System et Skype Entreprise.
  
## <a name="trusted-domains"></a>Domaines approuvés

Le client Skype Entreprise affiche une boîte de dialogue qui permet aux utilisateurs d’accepter le certificat du serveur Skype Entreprise si le domaine SIP du compte d’utilisateur qui se signe est différent du nom présenté dans l’objet ou l’autre nom de l’objet sur le certificat. Si le certificat configuré pour Skype Entreprise Server dans votre organisation n’a pas le nom de domaine SIP du compte Skype Room System dans l’objet ou l’autre nom de l’objet, vous devez configurer les domaines présentés sur le certificat sous la clé de Registre Domaines de confiance sur la console Skype Room System. Le Guide de l’administrateur Skype Room System fourni par le fabricant de Skype Room System explique comment et où ajouter des domaines de confiance dans le client Skype Entreprise. 
  
Par exemple, supposons que les certificats configurés sur Skype Entreprise Server ont un autre nom d’objet/d’objet « CONTOSO ». LOCAL » et l’un des domaines SIP affectés à un utilisateur pour l’adresse de la conférence Skype Room System est « confrm1@contoso.net ». Étant donné que contoso.net ne se trouve pas dans le certificat, sur l’ordinateur Skype Room System, vous devez configurer « contoso.local » en tant que domaine approuvé dans le Registre, comme expliqué dans le Guide de l’administrateur skype Room System fourni par le fabricant de Skype Room System. 
  

