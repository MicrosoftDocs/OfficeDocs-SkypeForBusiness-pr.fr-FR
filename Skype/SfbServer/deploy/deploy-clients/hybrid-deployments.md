---
title: Déploiements hybrides de Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lisez cette rubrique pour savoir comment déployer le système d’espace Skype dans un environnement hybride.
ms.openlocfilehash: e4ef63ec39106a2cb35201d43ca012b4ce173911
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-hybrid-deployments"></a>Déploiements hybrides de Skype Room System
 
Lisez cette rubrique pour savoir comment déployer le système d’espace Skype dans un environnement hybride.
  
## <a name="hybrid-deployments"></a>Déploiements hybrides

Si votre topologie inclut Skype pour Business Server et Exchange Online, et que vous souhaitez héberger la boîte aux lettres de ressource système de salle Skype sur Exchange Online, procédez comme suit. Cette section décrit également un scénario hybride où vous avez déployé à la fois Exchange Online et Exchange Server.
  
À des fins d’illustration, nous utilisons LyncSample.com pour le domaine de locaux et LyncSample.ccstp.net pour le domaine en ligne.
  
1. Créer une boîte aux lettres de ressources dans le centre d’administration Exchange (LyncSample.ccsctp.net) en vous connectant à l’interface de gestion en ligne d’Exchange, comme décrit dans la mise en service en ligne d’Exchange.
    
  ```
  New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
  ```

    Vous pouvez vérifier la connectivité OWA pour se connecter à l’aide de lrstest5@LyncSample.ccsctp.net.
    
2. Dans le centre d’administration Office 365 Exchange, ajouter un courrier électronique adresse lrstest5@LyncSample.com (domaine sur prem) et le définir comme adresse de réponse.
    
3. Créer une sous-prem Active Directory utilisateur lrstest5@LyncSample.com, la valeur lrstest5@LyncSample.com l’adresse de messagerie et l’adresse cible la valeur lrstest5@LyncSample.com.
    
4. Déclencher la synchronisation d’annuaire et, une fois la synchronisation terminée, vérifiez que les utilisateurs fusionner dans DAS et que vous n’êtes pas en mesure de modifier les propriétés des ressources de destinataire dans le centre d’administration Exchange d’Office 365.
    
5. Vérifiez la connectivité OWA à l’aide de lrstest5@LyncSample.com. (Version antérieure, vous vérifiez la connectivité OWA en utilisant le domaine en ligne.)
    
    Après avoir créé la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing dans l’Exchange Online Management Shell pour configurer la boîte aux lettres. Reportez-vous aux étapes 3 à 6 sous Déploiements locaux dans une forêt unique pour plus d’informations.
    
    > [!NOTE]
    > Si vous disposez d’un environnement hybride avec Exchange Server et Exchange Online, accédez à le lrstest5@LyncSample.mail.ccsctp.net Exchange Management Shell et activer-RemoteMailbox lrstest5@LyncSample.com - RemoteRoutingAddress-salle. Puis enclenchez la synchronisation d’annuaires. 
  
    Si vous souhaitez héberger la boîte aux lettres système de salle Skype dans Exchange en ligne, ces étapes d’Exchange Management Shell ne sont pas nécessaires et vous pouvez passer à l’étape 6.
    
6. Activer le compte système local de Skype pour Skype pour entreprise en exécutant l’applet de commande suivant sur Skype pour Business Management Shell :
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si vous avez Skype pour entreprise en ligne au lieu de Skype pour Business Server dans le scénario ci-dessus, puis après la mise en service de la boîte aux lettres de ressources Exchange, mettre en service un Skype pour compte professionnel comme décrit dans Skype pour les professionnels de la mise en service en ligne. 
  

