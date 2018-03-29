---
title: Planification de stratégies d’emplacement dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Lisez cette rubrique pour savoir comment planifier des stratégies d’emplacement pour un déploiement de services d’urgence améliorés (E9-1-1) dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 246a4bcddece986d9488c5e2bccbbece5f1a2cc9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-location-policies-for-skype-for-business-server-2015"></a>Planification de stratégies d’emplacement dans Skype Entreprise Server 2015
 
Lisez cette rubrique pour savoir comment planifier des stratégies d’emplacement pour un déploiement de services d’urgence améliorés (E9-1-1) dans Skype pour Business Server Voix Entreprise. 
  
> [!NOTE]
> Skype pour Business Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Si vous souhaitez configurer plusieurs numéros d’urgence, vous devez suivre les informations de [planifier plusieurs numéros d’urgence dans Skype pour Business Server 2015](multiple-emergency-numbers.md) et [configurer plusieurs numéros d’urgence dans Skype pour entreprise 2015](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
Vous créez des stratégies d’emplacement à l’aide de la Skype pour le panneau d’entreprise ou à l’aide de l’applet de commande [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) . Pour plus d’informations, consultez [créer des stratégies d’emplacement dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Chaque stratégie d’emplacement renferme les informations suivantes :
  
 **Activation d'Enhanced 9-1-1**
  
Si cette valeur est activée, le client est activé pour les services d’urgence étendus (E9-1-1). Lorsqu’un client enregistre, il tente d’acquérir un emplacement à partir du service d’informations d’emplacement et inclut les informations d’emplacement dans le cadre d’un appel d’urgence.
  
 **Emplacement**
  
Ce paramètre est utilisé uniquement lorsque **l’activation Enhanced 9-1-1** est activée.
  
Vous pouvez configurer le paramètre **Emplacement** pour définir le comportement du client de la manière suivante :   
  
- Si vous sélectionnez **Non **, l’utilisateur ne sera pas invité à entrer un emplacement.
    
- Si vous sélectionnez **Oui **, l’utilisateur sera invité à entrer un emplacement, mais pourra ignorer le message d’invite.
    
- Si vous sélectionnez **Clause d’exclusion de responsabilité **, l’utilisateur sera invité à entrer un emplacement, et une notification d’exclusion s’affichera également s’il essaie d’ignorer le message d’invite. Dans tous les cas, l'utilisateur peut continuer d'utiliser le client.
    
> [!NOTE]
> Le texte de la clause d’exclusion de responsabilité ne s’affiche pas si un utilisateur a entré manuellement un emplacement avant d’avoir été activé pour E9-1-1. Les mises à jour apportées à ce texte ne s’afficheront pas pour les utilisateurs ayant déjà pris connaissance de la clause d’exclusion de responsabilité.  
  
 **Clause d’exclusion de responsabilité du service d’urgence**
  
Ce paramètre spécifie la clause d’exclusion de responsabilité qui s’affiche si les utilisateurs ignorent l’invite pour un emplacement. Dans Skype pour Business Server, vous pouvez utiliser la stratégie de l’emplacement pour définir des exclusions de responsabilité différentes pour différents paramètres régionaux ou à différents groupes d’utilisateurs.
  
 **Chaîne de numérotation d’urgence (numéro E9-1-1)**
  
Cette chaîne de connexion (moins l’interligne « + », mais ne comprenant aucune normalisation effectuée par Dial Plan l’utilisateur) signifie qu’un appel est un appel d’urgence. La **chaîne de numérotation d’urgence** oblige le client à inclure dans l’appel les informations d’emplacement et de rappel.
  
> [!NOTE]
> Si votre organisation n’utilise pas un préfixe d’accès de ligne externe, vous n’avez pas besoin de créer une règle correspondante normalisation Plan de numérotation qui ajoute un « + » à la chaîne 911 avant d’envoyer l’appel de routage sortant sur un serveur exécutant Skype pour le serveur de l’entreprise ; le « + » sera automatiquement placé par le Skype pour client d’entreprise à la suite de la stratégie de l’emplacement. Toutefois, si votre site utilise un préfixe d’accès externe, vous devez ajouter une règle de normalisation à la stratégie de Plan de numérotation applicable qui supprime le préfixe d’accès externe et ajoute le « + ». Par exemple, si votre magasin utilise un préfixe d’accès externe de 9 et si un utilisateur connecte à 9 911 pour placer un appel d’urgence, le client utilisera sa stratégie de Plan de numérotation à cette normalisation à +911 avant le le numéro composé est évalué par les itinéraires dans le profil d’emplacement de l’appelant. 
  
 **Masques de chaîne de numérotation d’urgence (masque E9-1-1)**
  
Séparées par des points-virgules liste de chaînes de connexion qui est traduite dans la **Chaîne d’appel d’urgence**de spécifié. Par exemple, vous souhaiterez ajouter 112, qui est le numéro de service d’urgence pour la plupart de l’Europe. Une visite Skype pour les utilisateurs des entreprises d’Europe ne savez ne peut-être pas que 911 est le numéro d’urgence américain, mais ils peuvent composer 112 et obtenir le même résultat. Comme avec la chaîne de numérotation d’urgence, n’incluez ne pas un « + » avant chaque numéro, et si vous utilisez les codes d’accès de ligne externe, veillez à il y a des règles de normalisation dans la stratégie de Plan de numérotation de l’utilisateur pour supprimer, désactiver le chiffre du code d’accès.
  
 **Utilisation PSTN**
  
Nom de l’utilisation PSTN qui contient les chemins de routage qui déterminent la jonction SIP, la passerelle PSTN ou la passerelle ELIN vers laquelle les appels seront acheminés.
  
> [!NOTE]
> Seule une utilisation peut être affectée à une stratégie d’emplacement. Cette utilisation RTPC substitue les utilisations RTPC attribuée à la stratégie de voix de l’utilisateur, mais s’applique uniquement aux appels effectués à la chaîne de numérotation d’urgence ou à l’un des masques de chaîne d’urgence à distance. 
  
 **URI de notification**
  
Indique les URI SIP des membres du personnel de sécurité qui reçoivent une notification de messagerie instantanée en cas d’appel d’urgence. Les groupes de distribution sont pris en charge.
  
 **URI de la conférence**
  
Indique le numéro SDA (en général, numéro de service de sécurité) qui doit participer à la conférence en cas d’appel d’urgence.   
  
 **Mode Conférence**
  
Indique si l’URI de conférence participera à l’appel d’urgence via une communication unidirectionnelle ou bidirectionnelle.  
  
 **Intervalle d’actualisation d’emplacement**
  
Spécifie l’intervalle de temps (en heures) entre les requêtes des clients pour une mise à jour de l’emplacement à partir du service d’informations d’emplacement. La valeur peut être comprise entre 1 et 12. La valeur par défaut est 4.
  

