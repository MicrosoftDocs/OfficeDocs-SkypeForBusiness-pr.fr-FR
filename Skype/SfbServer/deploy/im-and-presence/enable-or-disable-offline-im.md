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
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a><span data-ttu-id="5f07d-103">Activation ou désactivation de la messagerie instantanée hors ligne dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5f07d-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5f07d-104">Apprenez à activer ou désactiver les hors connexion messagerie instantanée (IM) dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5f07d-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server 2015.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a><span data-ttu-id="5f07d-105">Activer en mode hors connexion la messagerie instantanée (MI) dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5f07d-105">Enable Offline Instant Messaging (IM) in Skype for Business Server 2015</span></span>

<span data-ttu-id="5f07d-106">Messagerie instantanée en mode hors connexion est une fonctionnalité de côté de client intégrée à Skype pour client d’entreprise (2016 C2R build 16.0.6701.1000 ou version ultérieure) qui s’appuie sur Exchange Web Services (EWS) pour envoyer des messages à partir de la Skype pour client d’entreprise pour la boîte aux lettres Exchange de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5f07d-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="5f07d-107">Hors connexion messagerie instantanée utilise Exchange Web Services (EWS) pour envoyer des messages en mode hors connexion à partir de la Skype pour client d’entreprise à la boîte aux lettres du destinataire.</span><span class="sxs-lookup"><span data-stu-id="5f07d-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="5f07d-108">EWS doit être disponible pour le Skype pour client d’entreprise pour envoyer des messages en mode hors connexion.</span><span class="sxs-lookup"><span data-stu-id="5f07d-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="5f07d-109">Pour en savoir plus sur la planification de la messagerie instantanée et de présence, afficher un [Plan pour la messagerie instantanée et de présence dans Skype pour Business Server 2015](../../plan-your-deployment/instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="5f07d-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server 2015](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f07d-110">Si la boîte aux lettres de l’utilisateur est hébergé dans Exchange sur site, le Skype pour client d’entreprise (2016 C2R build 16.0.6920.1000) est requis</span><span class="sxs-lookup"><span data-stu-id="5f07d-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server-2015-with-cu3"></a><span data-ttu-id="5f07d-111">Pour activer ou désactiver en mode hors connexion par messagerie instantanée Skype pour 2015 de serveur d’entreprise avec CU3</span><span class="sxs-lookup"><span data-stu-id="5f07d-111">To enable or disable Offline IM in Skype for Business Server 2015 with CU3</span></span>

1. <span data-ttu-id="5f07d-112">Ouvrez le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5f07d-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="5f07d-113">Exécutez la commande suivante pour activer la messagerie instantanée hors ligne.</span><span class="sxs-lookup"><span data-stu-id="5f07d-113">Run the following command to enable Offline IM.</span></span>
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="5f07d-114">Dans Skype pour Business Server 2015 CU3, l’option EnableOfflineIM est définie sur $True par défaut.</span><span class="sxs-lookup"><span data-stu-id="5f07d-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="5f07d-115">Pour désactiver, définissez-la sur $False.</span><span class="sxs-lookup"><span data-stu-id="5f07d-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="5f07d-116">Exécutez la commande suivante pour vérifier la capacité de stocker de hors connexion la messagerie instantanée est définie.</span><span class="sxs-lookup"><span data-stu-id="5f07d-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="5f07d-117">Intégration de la messagerie instantanée hors ligne à Exchange</span><span class="sxs-lookup"><span data-stu-id="5f07d-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="5f07d-p103">La messagerie instantanée hors ligne ne sera pas disponible pour les expéditeurs s'ils disposent d'une stratégie client qui désactive l'enregistrement automatique des messages hors ligne dans le dossier d'historique des conversations (EnableIMAutoArchiving = $false). Il n'existe aucun mécanisme permettant de vérifier si le destinataire est en mesure de recevoir les messages hors ligne.</span><span class="sxs-lookup"><span data-stu-id="5f07d-p103">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false). There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="5f07d-120">Ils seront reçus sous la forme d’un message électronique avec une classe de message de la messagerie instantanée des messages en mode hors connexion dans la même organisation. Note.MissedConversation et doit figurer dans les dossiers Outlook **Manqué une Conversation** , ainsi que l’historique de conversation qui est reprise dans l’onglet de l’historique récent liste/conversation dans Skype pour les clients de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="5f07d-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="5f07d-121">Les messages hors ligne envoyés à partir d'une organisation fédérée seront reçus sous forme d'e-mail sans IM.Note.MisssedConversation et ne seront pas récupérés dans les dossiers de conversation manquée ni d'historique des conversations.</span><span class="sxs-lookup"><span data-stu-id="5f07d-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="5f07d-122">Identification et résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="5f07d-122">Troubleshooting</span></span>

<span data-ttu-id="5f07d-123">Il existe un minuteur de deux minutes à partir de quand un message en mode hors connexion est envoyé à lorsqu’il a décroché et traitées.</span><span class="sxs-lookup"><span data-stu-id="5f07d-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="5f07d-124">Si les messages en mode hors connexion ne peut pas être traitées, ils apparaîtront dans le répertoire suivant :</span><span class="sxs-lookup"><span data-stu-id="5f07d-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
   ```
  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler
  ```

<span data-ttu-id="5f07d-125">Le Skype principal pour les journaux ETL d’entreprise contient des informations sur le traitement des messages en mode hors connexion et est votre meilleure source d’enquête/dépannage.</span><span class="sxs-lookup"><span data-stu-id="5f07d-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5f07d-p105">Un problème lié à l'échec de l'envoi des messages hors ligne et au dossier Brouillons saturé de messages a été signalé. Ce problème survenait avec les boîtes aux lettres Exchange sur site et a été résolu dans tous les canaux C2R depuis le 14/06/2016. </span><span class="sxs-lookup"><span data-stu-id="5f07d-p105">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages. This occurred with Exchange On-Premises mailboxes. The issue has been fixed in all C2R channels as of 6/14/2016.</span></span> 
  

