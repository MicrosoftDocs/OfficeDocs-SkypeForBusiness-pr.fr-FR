---
title: Déploiements hybrides de Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lisez cette rubrique pour savoir comment déployer Skype salle système dans un environnement hybride.
ms.openlocfilehash: 2f48707fd4e247a952bc17d26284a8a29eba025a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895172"
---
# <a name="skype-room-system-hybrid-deployments"></a>Déploiements hybrides de Skype Room System

Lisez cette rubrique pour savoir comment déployer Skype salle système dans un environnement hybride.
  
## <a name="hybrid-deployments"></a>Déploiements hybrides

Si votre topologie a Skype pour Business Server et Exchange Online, et que vous souhaitez héberger la boîte aux lettres de ressources système de salle Skype dans Exchange Online, procédez comme suit. Cette section décrit également un scénario hybride où vous avez déployé à la fois Exchange Online et Exchange Server.
  
À des fins d’illustration, nous utilisons LyncSample.com pour le domaine local et LyncSample.ccstp.net pour le domaine en ligne.
  
1. Créer une boîte aux lettres de ressources dans le centre d’administration Exchange (LyncSample.ccsctp.net) à se connecter à Exchange Online Management shell, comme décrit dans la mise en service en ligne d’Exchange.
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Vous pouvez vérifier la connectivité OWA pour se connecter à l’aide de lrstest5@LyncSample.ccsctp.net.
    
2. Dans le centre d’administration Office 365 Exchange, ajouter un e-mail adresse lrstest5@LyncSample.com (domaine sur prem) et le définir comme adresse de réponse.
    
3. Créer un sur prem Active Directory utilisateur lrstest5@LyncSample.com, définir l’adresse de messagerie à lrstest5@LyncSample.com et définir l’adresse cible à lrstest5@LyncSample.com.
    
4. Déclenche la synchronisation d’annuaires et, une fois la synchronisation terminée, vérifiez que les utilisateurs de fusion dans DAS et que vous n’êtes pas en mesure de modifier les propriétés dans les ressources du destinataire dans le centre d’administration Exchange Office 365.
    
5. Vérifiez la connectivité OWA à l’aide de lrstest5@LyncSample.com. (Précédemment, vous vérifié la connectivité OWA à l’aide du domaine en ligne.)
    
    Après avoir créé la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing dans l’Exchange Online Management Shell pour configurer la boîte aux lettres. Reportez-vous aux étapes 3 à 6 sous Déploiements locaux dans une forêt unique pour plus d’informations.
    
   > [!NOTE]
   > Si vous avez un environnement hybride avec Exchange Server et Exchange Online, accédez à la lrstest5@LyncSample.mail.ccsctp.net Exchange Management Shell et Enable-RemoteMailbox lrstest5@LyncSample.com - RemoteRoutingAddress-salle. Puis enclenchez la synchronisation d’annuaires. 
  
    Si vous souhaitez héberger la boîte aux lettres système de salle Skype dans Exchange Online, ces étapes Exchange Management Shell ne sont pas requis et vous pouvez passer à l’étape 6.
    
6. Activer le compte de système de salle Skype pour Skype pour les entreprises en exécutant l’applet de commande suivante sur Skype pour Business Management Shell :
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si vous avez Skype pour Business Online au lieu de Skype pour Business Server dans l’exemple ci-dessus, après la mise en service de la boîte aux lettres de ressources Exchange, configurer un Skype pour un compte professionnel comme indiqué dans Skype pour la mise en service en ligne de l’entreprise. 
  

