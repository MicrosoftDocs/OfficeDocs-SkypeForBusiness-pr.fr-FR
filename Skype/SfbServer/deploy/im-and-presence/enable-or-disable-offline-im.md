---
title: Activer ou désactiver en mode hors connexion la messagerie instantanée dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Apprenez à activer ou désactiver en mode hors connexion de messagerie instantanée dans Skype pour Business Server.
ms.openlocfilehash: 29342f3903e58f90ab4d2a939be6cd20d3f8e31b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217662"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Activer ou désactiver en mode hors connexion la messagerie instantanée dans Skype pour Business Server
 
Apprenez à activer ou désactiver en mode hors connexion de messagerie instantanée dans Skype pour Business Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Activer en mode hors connexion la messagerie instantanée dans Skype pour Business Server

Messagerie instantanée en mode hors connexion est une fonctionnalité de côté client intégrée Skype pour client d’entreprise (2016 C2R build 16.0.6701.1000 ou ultérieure) qui tire parti des Services Web Exchange (EWS) pour envoyer des messages à partir de la Skype pour client d’entreprise pour la boîte aux lettres Exchange de l’utilisateur. Hors connexion de messagerie instantanée utilise Exchange Web Services (EWS) pour envoyer des messages en mode hors connexion à partir de la Skype pour client d’entreprise pour la boîte aux lettres du destinataire. EWS doit être disponible pour le Skype pour client d’entreprise pour envoyer des messages en mode hors connexion. Pour en savoir plus sur la planification de la messagerie instantanée et présence, voir [planification de la messagerie instantanée et présence dans Skype pour Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Si la boîte aux lettres de l’utilisateur est hébergé dans Exchange locale, le Skype pour client d’entreprise (2016 C2R build 16.0.6920.1000) est requis 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Pour activer ou désactiver en mode hors connexion par messagerie instantanée Skype pour Business Server

1. Ouvrez le Skype pour Business Server Management Shell.
    
2. Exécutez la commande suivante pour activer la messagerie instantanée hors ligne.
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > Dans Skype pour Business Server 2015 CU3, l’option EnableOfflineIM est définie sur $True par défaut. Pour désactiver, définissez-la sur $False. 
  
3. Exécutez la commande suivante pour vérifier la valeur de la capacité de stocker d’en mode hors connexion la messagerie instantanée.
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Intégration de la messagerie instantanée hors ligne à Exchange

La messagerie instantanée hors ligne ne sera pas disponible pour les expéditeurs s'ils disposent d'une stratégie client qui désactive l'enregistrement automatique des messages hors ligne dans le dossier d'historique des conversations (EnableIMAutoArchiving = $false). Il n'existe aucun mécanisme permettant de vérifier si le destinataire est en mesure de recevoir les messages hors ligne.
  
Ils seront reçues en tant qu’un message électronique avec la classe de message de messagerie instantanée pour les messages envoyés au sein de la même organisation hors connexion. Note.MissedConversation et ne sont inclus dans le dossier Outlook **Conversations manquées** , ainsi que l’historique des conversations qui seront reprises dans récents onglet liste/conversation historique Skype pour les clients d’entreprise.
  
Les messages hors ligne envoyés à partir d'une organisation fédérée seront reçus sous forme d'e-mail sans IM.Note.MisssedConversation et ne seront pas récupérés dans les dossiers de conversation manquée ni d'historique des conversations. 
  
## <a name="troubleshooting"></a>Identification et résolution des problèmes

Il existe un minuteur de deux minutes de lorsqu’un message en mode hors connexion est envoyé à lorsqu’il a choisie et traités. Si les messages en mode hors connexion ne peut pas être traitées apparaîtront dans le répertoire suivant : 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

Le principal Skype pour journal ETL Business contient des informations sur le traitement des messages en mode hors connexion et est votre meilleure source d’enquête/la résolution des problèmes. 
  
> [!NOTE]
> Un problème lié à l'échec de l'envoi des messages hors ligne et au dossier Brouillons saturé de messages a été signalé. Ce problème survenait avec les boîtes aux lettres Exchange sur site et a été résolu dans tous les canaux C2R depuis le 14/06/2016.   
