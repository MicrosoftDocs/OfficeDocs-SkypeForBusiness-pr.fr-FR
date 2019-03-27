---
title: Planifier des stratégies d’emplacement de Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Lisez cette rubrique pour savoir comment planifier des stratégies d’emplacement pour un déploiement de services d’urgence étendus (E9-1-1) dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 6717d6b7940ccf9cf7de403797d8bd4712f18144
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878020"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planifier des stratégies d’emplacement de Skype pour Business Server
 
Lisez cette rubrique pour savoir comment planifier des stratégies d’emplacement pour un déploiement de services d’urgence étendus (E9-1-1) dans Skype pour Business Server Enterprise Voice. 
  
> [!NOTE]
> Skype pour Business Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Si vous souhaitez configurer plusieurs numéros d’urgence, vous devez suivre les informations de [planifier plusieurs numéros d’urgence dans Skype pour Business Server](multiple-emergency-numbers.md) et [configurer plusieurs numéros d’urgence dans Skype pour les entreprises](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
Vous créez des stratégies d’emplacement à l’aide de la Skype pour Business le panneau de configuration ou à l’aide de l’applet de commande [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) . Pour plus d’informations, voir [Create stratégies d’emplacement Skype pour Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Chaque stratégie d’emplacement renferme les informations suivantes :
  
 **Activation d'Enhanced 9-1-1**
  
Si cette valeur est activée, le client est activé pour les services d’urgence étendus (E9-1-1). Lorsqu’un client enregistre, il essaie d’acquisition d’un emplacement à partir du service informations d’emplacement et inclut les informations d’emplacement dans le cadre d’un appel d’urgence.
  
 **Emplacement**
  
Ce paramètre est utilisé uniquement lorsque l'**activation d'Enhanced 9-1-1** est activée. 
  
Vous pouvez configurer le paramètre **Emplacement** pour définir le comportement du client de la manière suivante :   
  
- Si vous sélectionnez **Non **, l’utilisateur ne sera pas invité à entrer un emplacement.
    
- Si vous sélectionnez **Oui **, l’utilisateur sera invité à entrer un emplacement, mais pourra ignorer le message d’invite.
    
- Si vous sélectionnez **Clause d’exclusion de responsabilité **, l’utilisateur sera invité à entrer un emplacement, et une notification d’exclusion s’affichera également s’il essaie d’ignorer le message d’invite. Dans tous les cas, l'utilisateur peut continuer d'utiliser le client.
    
> [!NOTE]
> Le texte de la clause d’exclusion de responsabilité ne s’affiche pas si un utilisateur a entré manuellement un emplacement avant d’avoir été activé pour E9-1-1. Les mises à jour apportées à ce texte ne s’afficheront pas pour les utilisateurs ayant déjà pris connaissance de la clause d’exclusion de responsabilité.  
  
 **Clause d’exclusion de responsabilité du service d’urgence**
  
Ce paramètre spécifie la clause d’exclusion de responsabilité qui s’affiche si les utilisateurs ignorent l’invite pour un emplacement. Dans Skype pour Business Server, vous pouvez utiliser la stratégie d’emplacement pour définir les clauses d’exclusion différentes pour différents groupes d’utilisateurs ou de différents paramètres régionaux.
  
 **Chaîne de numérotation d’urgence (numéro E9-1-1)**
  
Cette chaîne de numérotation (moins le signe « + », mais y compris les normalisation effectuée par le Plan de numérotation de l’utilisateur) signifie qu’un appel est un appel d’urgence. La **chaîne de numérotation d’urgence** oblige le client à inclure dans l’appel les informations d’emplacement et de rappel.
  
> [!NOTE]
> Si votre organisation n’utilise pas un préfixe d’accès de ligne externe, il est inutile créer une règle correspondante normalisation Plan de numérotation qui ajoute un « + » à la chaîne 911 avant l’envoi de l’appel vers le routage sortant sur un serveur exécutant Skype pour Business Server ; le « + » est automatiquement ajoutée à la Skype pour client d’entreprise à la suite de la stratégie d’emplacement. Toutefois, si votre site utilise un préfixe d’accès externe, vous devez ajouter une règle de normalisation à la stratégie de Plan de numérotation applicable qui supprime le préfixe d’accès externe et ajoute le « + ». Par exemple, si votre emplacement utilise un préfixe d’accès externe de 9 et un utilisateur compose 9 911 pour mettre un appel d’urgence, le client utilisera sa stratégie de Plan de numérotation pour normaliser cela à +911 avant le numéro composé est évalué par les itinéraires dans le profil d’emplacement de l’appelant. 
  
 **Masques de chaîne de numérotation d’urgence (masque E9-1-1)**
  
Séparées par des points-virgules liste de chaînes de numérotation est converti en la **Chaîne de numérotation d’urgence**spécifiée. Par exemple, vous souhaiterez peut-être ajouter 112, qui est le numéro de service d’urgence pour la plupart des Europe. Une visite Skype pour utilisateur Business Europe ne savez ne peut-être pas 911 est le numéro d’urgence américain, mais ils peuvent composer 112 et obtenir le même résultat. Comme avec la chaîne de numérotation d’urgence, n’incluez ne pas « + » avant chaque numéro, et si vous utilisez les codes d’accès de ligne externe, assurez-vous que règles de normalisation dans la stratégie de Plan de numérotation de l’utilisateur à supprimer désactive le chiffre du code d’accès.
  
 **Utilisation PSTN**
  
Nom de l’utilisation PSTN qui contient les chemins de routage qui déterminent la jonction SIP, la passerelle PSTN ou la passerelle ELIN vers laquelle les appels seront acheminés.
  
> [!NOTE]
> Seule une utilisation peut être affectée à une stratégie d’emplacement. Cette utilisation PSTN remplace les utilisations PSTN assignées à la stratégie de voix de l’utilisateur, mais s’applique uniquement aux appels passés à la chaîne de numérotation d’urgence ou à l’un des masques de chaîne de numérotation d’urgence. 
  
 **URI de notification**
  
Indique les URI SIP des membres du personnel de sécurité qui reçoivent une notification de messagerie instantanée en cas d’appel d’urgence. Les groupes de distribution sont pris en charge.
  
 **URI de la conférence**
  
Indique le numéro SDA (en général, numéro de service de sécurité) qui doit participer à la conférence en cas d’appel d’urgence.   
  
 **Mode Conférence**
  
Indique si l’URI de conférence participera à l’appel d’urgence via une communication unidirectionnelle ou bidirectionnelle.  
  
 **Intervalle d’actualisation d’emplacement**
  
Spécifie la quantité de temps (en heures) entre les demandes des clients pour une mise à jour de l’emplacement du service informations d’emplacement. La valeur peut être comprise entre 1 et 12. La valeur par défaut est 4.
  

