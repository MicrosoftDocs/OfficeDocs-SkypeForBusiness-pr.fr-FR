---
title: Activation ou désactivation de la messagerie instantanée hors connexion dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Apprenez à activer ou désactiver la messagerie instantanée hors connexion dans Skype entreprise Server.
ms.openlocfilehash: 363f7c54d682dc619417a8d9601c7beafc8283c6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235546"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Activation ou désactivation de la messagerie instantanée hors connexion dans Skype entreprise Server
 
Apprenez à activer ou désactiver la messagerie instantanée hors connexion dans Skype entreprise Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Activation de la messagerie instantanée hors connexion dans Skype entreprise Server

La fonction de messagerie instantanée hors connexion est une fonctionnalité côté client intégrée au client Skype entreprise (2016 C2R Build 16.0.6701.1000 ou version ultérieure) qui exploite les services Web Exchange (EWS) pour envoyer des messages à partir du client Skype entreprise vers la boîte aux lettres Exchange d’un utilisateur. Le mode mi hors connexion utilise les services Web Exchange (EWS) pour envoyer des messages hors connexion du client Skype entreprise vers la boîte aux lettres du destinataire. EWS doit être disponible pour le client Skype entreprise afin que les messages hors connexion puissent être envoyés. Pour en savoir plus sur la planification des messages instantanés et la présence, voir [planifier la messagerie instantanée et la présence dans Skype entreprise Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Si la boîte aux lettres de l’utilisateur est hébergée dans Exchange en local, le client Skype entreprise (2016 C2R Build 16.0.6920.1000) est requis 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Pour activer ou désactiver la messagerie instantanée hors connexion dans Skype entreprise Server

1. Ouvrez Skype entreprise Server Management Shell.
    
2. Exécutez la commande suivante pour activer la messagerie instantanée hors ligne.
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > Dans Skype entreprise Server 2015 CU3, l’option EnableOfflineIM est définie sur $True par défaut. Pour désactiver, définissez-la sur $False. 
  
3. Exécutez la commande suivante pour confirmer la possibilité de stocker les messages instantanés en mode hors connexion est défini.
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Intégration de la messagerie instantanée hors ligne à Exchange

La messagerie instantanée hors ligne ne sera pas disponible pour les expéditeurs s'ils disposent d'une stratégie client qui désactive l'enregistrement automatique des messages hors ligne dans le dossier d'historique des conversations (EnableIMAutoArchiving = $false). Il n'existe aucun mécanisme permettant de vérifier si le destinataire est en mesure de recevoir les messages hors ligne.
  
Pour les messages hors connexion envoyés au sein de la même organisation, ils sont reçus sous la forme d’un message électronique avec une classe de message instantané. Remarque. MissedConversation et sera inclus dans le dossier des **conversations manquées** d’Outlook, ainsi que dans l’historique des conversations qui sera sélectionné dans la boîte de message liste récente/historique des conversations dans les clients Skype entreprise.
  
Les messages hors ligne envoyés à partir d'une organisation fédérée seront reçus sous forme d'e-mail sans IM.Note.MisssedConversation et ne seront pas récupérés dans les dossiers de conversation manquée ni d'historique des conversations. 
  
## <a name="troubleshooting"></a>Identification et résolution des problèmes

Le délai d’envoi d’un message hors connexion lors de la sélection et du traitement d’un message hors connexion est de deux minutes. Si les messages hors connexion ne peuvent pas être traités, ils s’affichent dans l’annuaire suivant: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

Le journal ETL principal de Skype entreprise contient des informations sur le traitement des messages hors ligne et constitue votre meilleure source d’investigation et de résolution des problèmes. 
  
> [!NOTE]
> Un problème lié à l'échec de l'envoi des messages hors ligne et au dossier Brouillons saturé de messages a été signalé. Ce problème survenait avec les boîtes aux lettres Exchange sur site et a été résolu dans tous les canaux C2R depuis le 14/06/2016.   
