---
title: Activer ou désactiver la messagerie instantanée hors connexion dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Découvrez comment activer ou désactiver la messagerie instantanée hors connexion dans Skype Entreprise Server.
ms.openlocfilehash: aace1ca45c224ce6ef6c7d6d6f151ecd3ab9b260
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858631"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Activer ou désactiver la messagerie instantanée hors connexion dans Skype Entreprise Server
 
Découvrez comment activer ou désactiver la messagerie instantanée hors connexion dans Skype Entreprise Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Activer la messagerie instantanée hors connexion dans Skype Entreprise Server

La messagerie instantanée hors connexion est une fonctionnalité côté client intégrée au client Skype Entreprise (version 2016 C2R 16.0.6701.1000 ou supérieure) qui exploite les services web Exchange (EWS) pour envoyer des messages du client Skype Entreprise vers la boîte aux lettres Exchange d’un utilisateur. La messagerie instantanée hors connexion utilise Exchange Web Services (EWS) pour envoyer des messages hors connexion du client Skype Entreprise à la boîte aux lettres du destinataire. EWS doit être disponible pour le client Skype Entreprise pour que les messages hors connexion soient envoyés. Pour en savoir plus sur la planification de la messagerie instantanée et de la présence, voir Planifier la messagerie instantanée et [la présence dans Skype Entreprise Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Si la boîte aux lettres de l’utilisateur est hébergée dans Exchange local, le client Skype Entreprise (build 16.0.6920.1000 C2R 2016) est requis. 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Pour activer ou désactiver la messagerie instantanée hors connexion dans Skype Entreprise Server

1. Ouvrez l Skype Entreprise Server Management Shell.
    
2. Exécutez la commande suivante pour activer la messagerie instantanée hors connexion.
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > Dans Skype Entreprise Server CU3 2015, l’option EnableOfflineIM est définie sur $True par défaut. Pour désactiver, définissez cette valeur sur $False. 
  
3. Exécutez la commande suivante pour confirmer que la possibilité de stocker des messageries instantanées hors connexion est définie.
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Intégration de la messagerie instantanée hors connexion Exchange

La messagerie instantanée hors connexion n’est pas disponible pour les expéditeurs s’ils disposent d’une stratégie de client qui désactive l’enregistrement automatique des messages hors connexion dans le dossier d’historique des conversations (EnableIMAutoArchiving = $false). Il n’existe aucun mécanisme permettant de vérifier si le destinataire est en mesure de recevoir des messages hors connexion.
  
Pour les messages hors connexion envoyés au sein de la même organisation, ils sont reçus en tant que messages électroniques avec la classe de message IM.Note.MissedConversation et sont inclus dans le dossier Outlook **Missed Conversation,** ainsi que dans l’historique des conversations qui sera repris dans l’onglet liste récente/historique des conversations dans les clients Skype Entreprise.
  
Pour les messages hors connexion envoyés à partir d’une organisation fédérée, ils sont reçus en tant que messages électroniques sans IM.Note.MisssedConversation et ne sont pas pris en compte dans les dossiers de conversation manquée ou d’historique des conversations. 
  
## <a name="troubleshooting"></a>Résolution des problèmes

Il existe un minuteur de deux minutes entre le moment où un message hors connexion est envoyé et le moment où il est choisi et traitée. Si les messages hors connexion ne peuvent pas être traitées, ils apparaissent dans le répertoire suivant : 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

Le principal Skype Entreprise JOURNAL ETL contient des informations sur le traitement des messages hors connexion et constitue la meilleure source d’investigation/de dépannage. 
  
> [!NOTE]
> Un problème a été signalé lorsque les messages hors connexion n’ont pas pu être envoyés et que le dossier « Brouillons » était rempli de messages. Cela s’est produit Exchange boîtes aux lettres sur site. Le problème a été résolu dans tous les canaux C2R depuis le 14/06/2016.  
