---
title: Skype Domaines de confiance du système de salle
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lisez cette rubrique pour découvrir comment configurer des domaines de confiance pour Skype Room System et Skype Entreprise.
ms.openlocfilehash: 488b86e33035b39a1e189be7cc9191911250152e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830738"
---
# <a name="skype-room-system-trusted-domains"></a>Skype Domaines de confiance du système de salle
 
Lisez cette rubrique pour découvrir comment configurer des domaines de confiance pour Skype Room System et Skype Entreprise.
  
## <a name="trusted-domains"></a>Domaines approuvés

Le client Skype Entreprise affiche une boîte de dialogue qui permet aux utilisateurs d’accepter le certificat provenant du Skype Entreprise Server si le domaine SIP du compte d’utilisateur qui se signe est différent du nom présenté dans l’objet ou l’autre nom de l’objet sur le certificat. Si le certificat configuré pour Skype Entreprise Server dans votre organisation n’a pas le nom de domaine SIP du compte Skype Room System dans l’objet ou l’autre nom de l’objet, vous devez configurer les domaines présentés sur le certificat sous la clé de Registre Domaines de confiance sur la console Skype Room System. Le Guide de l’administrateur Skype Room System fourni par le fabricant Skype Room System explique comment et où ajouter des domaines de confiance dans le client Skype Entreprise client. 
  
Par exemple, supposons que les certificats configurés sur Skype Entreprise Server ont un autre nom d’objet/d’objet « CONTOSO ». LOCAL » et l’un des domaines SIP affectés à un utilisateur pour l’adresse de Skype Room System est « confrm1@contoso.net ». Comme contoso.net ne se trouve pas dans le certificat, sur l’ordinateur Skype Room System, vous devez configurer « contoso.local » en tant que domaine approuvé dans le Registre, comme expliqué dans le Guide de l’administrateur Skype Room System fourni par le fabricant de Skype Room System. 
  

