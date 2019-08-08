---
title: Déploiements hybrides de Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Pour plus d’informations sur le déploiement de votre système de salle Skype dans un environnement hybride, lisez cette rubrique.
ms.openlocfilehash: 016a4cf379200dc87b8f94d13a65f10f6c3af25f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234428"
---
# <a name="skype-room-system-hybrid-deployments"></a>Déploiements hybrides de Skype Room System

Pour plus d’informations sur le déploiement de votre système de salle Skype dans un environnement hybride, lisez cette rubrique.
  
## <a name="hybrid-deployments"></a>Déploiements hybrides

Suivez ces étapes si votre topologie utilise Skype entreprise Server et Exchange Online et si vous souhaitez héberger la boîte aux lettres de ressources du système de salle Skype sur Exchange Online. Cette section décrit également un scénario hybride où vous avez déployé à la fois Exchange Online et Exchange Server.
  
Pour des raisons d’illustration, nous utilisons LyncSample.com pour le domaine local et LyncSample.ccstp.net pour le domaine en ligne.
  
1. Pour créer une boîte aux lettres de ressources dans le centre d’administration Exchange (LyncSample.ccsctp.net), connectez-vous à Exchange Online Management Shell comme décrit dans la rubrique mise en service d’Exchange Online.
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Vous pouvez vérifier la connectivité OWA à l’aide de lrstest5@LyncSample.ccsctp.net pour vous connecter.
    
2. Dans le centre d’administration Exchange d’Office 365, ajoutez une adresse de messagerie lrstest5@LyncSample.com (domaine locaux), puis définissez-la comme adresse de réponse.
    
3. Créez un lrstest5@LyncSample.com de l’utilisateur Active Directory locaux, définissez l’adresse de messagerie sur lrstest5@LyncSample.com et définissez l’adresse cible sur lrstest5@LyncSample.com.
    
4. Déclenchez la synchronisation d’annuaires et, une fois la synchronisation terminée, vérifiez que les utilisateurs effectuent une fusion dans AAD et que vous ne pouvez pas modifier les propriétés des ressources du destinataire dans le centre d’administration Exchange d’Office 365.
    
5. Vérifiez la connectivité OWA à l’aide de lrstest5@LyncSample.com. (Auparavant, vous avez vérifié la connectivité OWA à l’aide du domaine en ligne.)
    
    Après avoir créé la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing dans l’Exchange Online Management Shell pour configurer la boîte aux lettres. Reportez-vous aux étapes 3 à 6 sous Déploiements locaux dans une forêt unique pour plus d’informations.
    
   > [!NOTE]
   > Si vous avez un environnement hybride avec Exchange Server et Exchange Online, accédez à Exchange Management Shell et activez-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-salle. Puis enclenchez la synchronisation d’annuaires. 
  
    Si vous souhaitez héberger la boîte aux lettres du système de salle Skype dans Exchange Online, ces étapes de l’interpréteur de tâches Exchange Management ne sont pas nécessaires et vous pouvez passer à l’étape 6.
    
6. Activez le compte système de salle Skype pour Skype entreprise en exécutant l’applet de commande suivante sur Skype entreprise Management Shell:
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si vous disposez de Skype entreprise Online au lieu de Skype entreprise Server dans le scénario ci-dessus, après la configuration de la boîte aux lettres de ressources Exchange, approvisionnez un compte Skype entreprise comme décrit dans la rubrique mise en service de Skype entreprise online. 
  

