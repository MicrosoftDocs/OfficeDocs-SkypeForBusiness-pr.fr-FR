---
title: Domaines approuvés de Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.
ms.openlocfilehash: 83d6e313f8643f593e1e25488e403da448649bd6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-trusted-domains"></a>Domaines approuvés de Skype Room System
 
Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.
  
## <a name="trusted-domains"></a>Domaines approuvés

Le Skype pour client d’entreprise affiche une boîte de dialogue qui permet aux utilisateurs d’accepter le certificat de la Skype pour Business Server si le domaine SIP de l’ouverture de session du compte d’utilisateur est différent de celui présenté dans l’objet ou le nom du sujet Alt sur le certificat. Si le certificat configuré pour Skype pour Business Server dans votre organisation n’a pas de nom de domaine SIP du compte système local de Skype dans l’objet ou le nom de l’objet Alt, vous devez configurer ces domaines présentés sur le certificat dans les domaines approuvés clé de Registre sur l’ordinateur de la console système de salle de Skype. Système de chambre de Skype fournie par le fabricant Skype espace système Guide de l’administrateur explique comment et où pour ajouter des domaines approuvés dans le Skype pour client d’entreprise. 
  
Par exemple, supposons que les certificats configurés sur Skype pour Business Server ont un nom objet/objet Alt « CONTOSO. « LOCAL » et l’un des domaines SIP affectés à un utilisateur pour l’adresse de connexion Skype espace système est « confrm1@contoso.net ». Car contoso.net n’est pas dans le certificat sur l’ordinateur du système de salle de Skype, vous devez configurer des « contoso.local » sous la forme d’un domaine approuvé dans le Registre, comme expliqué dans Skype espace système fournie par le fabricant Skype espace système Guide de l’administrateur. 
  

