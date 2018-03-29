---
title: Activation ou désactivation de la messagerie instantanée hors ligne dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Apprenez à activer ou désactiver les hors connexion messagerie instantanée (IM) dans Skype pour Business Server 2015.
ms.openlocfilehash: a9133ad82e4d25fae2aebd266273ecbb37c2a010
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a>Activation ou désactivation de la messagerie instantanée hors ligne dans Skype Entreprise Server 2015
 
Apprenez à activer ou désactiver les hors connexion messagerie instantanée (IM) dans Skype pour Business Server 2015.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a>Activer en mode hors connexion la messagerie instantanée (MI) dans Skype pour Business Server 2015

Messagerie instantanée en mode hors connexion est une fonctionnalité de côté de client intégrée à Skype pour client d’entreprise (2016 C2R build 16.0.6701.1000 ou version ultérieure) qui s’appuie sur Exchange Web Services (EWS) pour envoyer des messages à partir de la Skype pour client d’entreprise pour la boîte aux lettres Exchange de l’utilisateur. Hors connexion messagerie instantanée utilise Exchange Web Services (EWS) pour envoyer des messages en mode hors connexion à partir de la Skype pour client d’entreprise à la boîte aux lettres du destinataire. EWS doit être disponible pour le Skype pour client d’entreprise pour envoyer des messages en mode hors connexion. Pour en savoir plus sur la planification de la messagerie instantanée et de présence, afficher un [Plan pour la messagerie instantanée et de présence dans Skype pour Business Server 2015](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Si la boîte aux lettres de l’utilisateur est hébergé dans Exchange sur site, le Skype pour client d’entreprise (2016 C2R build 16.0.6920.1000) est requis 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server-2015-with-cu3"></a>Pour activer ou désactiver en mode hors connexion par messagerie instantanée Skype pour 2015 de serveur d’entreprise avec CU3

1. Ouvrez le Skype pour Business Server Management Shell.
    
2. Exécutez la commande suivante pour activer la messagerie instantanée hors ligne.
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > Dans Skype pour Business Server 2015 CU3, l’option EnableOfflineIM est définie sur $True par défaut. Pour désactiver, définissez-la sur $False. 
  
3. Exécutez la commande suivante pour vérifier la capacité de stocker de hors connexion la messagerie instantanée est définie.
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Intégration de la messagerie instantanée hors ligne à Exchange

La messagerie instantanée hors ligne ne sera pas disponible pour les expéditeurs s'ils disposent d'une stratégie client qui désactive l'enregistrement automatique des messages hors ligne dans le dossier d'historique des conversations (EnableIMAutoArchiving = $false). Il n'existe aucun mécanisme permettant de vérifier si le destinataire est en mesure de recevoir les messages hors ligne.
  
Ils seront reçus sous la forme d’un message électronique avec une classe de message de la messagerie instantanée des messages en mode hors connexion dans la même organisation. Note.MissedConversation et doit figurer dans les dossiers Outlook **Manqué une Conversation** , ainsi que l’historique de conversation qui est reprise dans l’onglet de l’historique récent liste/conversation dans Skype pour les clients de l’entreprise.
  
Les messages hors ligne envoyés à partir d'une organisation fédérée seront reçus sous forme d'e-mail sans IM.Note.MisssedConversation et ne seront pas récupérés dans les dossiers de conversation manquée ni d'historique des conversations. 
  
## <a name="troubleshooting"></a>Identification et résolution des problèmes

Il existe un minuteur de deux minutes à partir de quand un message en mode hors connexion est envoyé à lorsqu’il a décroché et traitées. Si les messages en mode hors connexion ne peut pas être traitées, ils apparaîtront dans le répertoire suivant : 
  
   ```
  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler
  ```

Le Skype principal pour les journaux ETL d’entreprise contient des informations sur le traitement des messages en mode hors connexion et est votre meilleure source d’enquête/dépannage. 
  
> [!NOTE]
> Un problème lié à l'échec de l'envoi des messages hors ligne et au dossier Brouillons saturé de messages a été signalé. Ce problème survenait avec les boîtes aux lettres Exchange sur site et a été résolu dans tous les canaux C2R depuis le 14/06/2016.  
  

