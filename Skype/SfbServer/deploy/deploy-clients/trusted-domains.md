---
title: Domaines approuvés de Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.
ms.openlocfilehash: b55d1558bd45cc8f0726b054fed60b2a4c5e4794
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983762"
---
# <a name="skype-room-system-trusted-domains"></a>Domaines approuvés de Skype Room System
 
Consultez cette rubrique pour apprendre à configurer des domaines approuvés pour Skype Room System et Skype Entreprise.
  
## <a name="trusted-domains"></a>Domaines approuvés

Le Skype pour Business client affiche une boîte de dialogue qui permet aux utilisateurs d’accepter le certificat à partir de la Skype pour Business Server si le domaine SIP du compte d’utilisateur la signature est différent de celui présenté dans l’objet ou l’autre nom du sujet du certificat. Si le certificat configuré pour Skype pour Business Server dans votre organisation ne dispose pas de nom de domaine SIP du compte de système de salle de Skype dans sujet ou autre nom du sujet, vous devez configurer ces domaines présentées dans le certificat sous les domaines approuvés clé de Registre sur l’ordinateur de la console Skype salle système. Votre système de salle Skype fournie par le fabricant Skype salle Guide administrateur système explique comment et où pour ajouter des domaines approuvés dans le Skype pour client d’entreprise. 
  
Par exemple, supposons que les certificats configurés sur Skype pour Business Server dont le nom du sujet/objet Alt de « CONTOSO. « LOCALE » et un des domaines SIP attribuées à un utilisateur pour l’adresse de connexion Skype salle système est « confrm1@contoso.net ». Car contoso.net n’est pas dans le certificat sur l’ordinateur du système de salle Skype, vous devez configurer « contoso.local » comme un domaine approuvé dans le Registre, comme expliqué dans votre système de salle Skype fournie par le fabricant Skype salle Guide administrateur système. 
  

