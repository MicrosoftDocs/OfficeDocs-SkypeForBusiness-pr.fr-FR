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
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="0ecb3-103">Activation ou désactivation de la messagerie instantanée hors connexion dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0ecb3-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="0ecb3-104">Apprenez à activer ou désactiver la messagerie instantanée hors connexion dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="0ecb3-105">Activation de la messagerie instantanée hors connexion dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0ecb3-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="0ecb3-106">La fonction de messagerie instantanée hors connexion est une fonctionnalité côté client intégrée au client Skype entreprise (2016 C2R Build 16.0.6701.1000 ou version ultérieure) qui exploite les services Web Exchange (EWS) pour envoyer des messages à partir du client Skype entreprise vers la boîte aux lettres Exchange d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="0ecb3-107">Le mode mi hors connexion utilise les services Web Exchange (EWS) pour envoyer des messages hors connexion du client Skype entreprise vers la boîte aux lettres du destinataire.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="0ecb3-108">EWS doit être disponible pour le client Skype entreprise afin que les messages hors connexion puissent être envoyés.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="0ecb3-109">Pour en savoir plus sur la planification des messages instantanés et la présence, voir [planifier la messagerie instantanée et la présence dans Skype entreprise Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="0ecb3-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0ecb3-110">Si la boîte aux lettres de l’utilisateur est hébergée dans Exchange en local, le client Skype entreprise (2016 C2R Build 16.0.6920.1000) est requis</span><span class="sxs-lookup"><span data-stu-id="0ecb3-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="0ecb3-111">Pour activer ou désactiver la messagerie instantanée hors connexion dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0ecb3-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="0ecb3-112">Ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="0ecb3-113">Exécutez la commande suivante pour activer la messagerie instantanée hors ligne.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-113">Run the following command to enable Offline IM.</span></span>
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="0ecb3-114">Dans Skype entreprise Server 2015 CU3, l’option EnableOfflineIM est définie sur $True par défaut.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="0ecb3-115">Pour désactiver, définissez-la sur $False.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="0ecb3-116">Exécutez la commande suivante pour confirmer la possibilité de stocker les messages instantanés en mode hors connexion est défini.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="0ecb3-117">Intégration de la messagerie instantanée hors ligne à Exchange</span><span class="sxs-lookup"><span data-stu-id="0ecb3-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="0ecb3-p103">La messagerie instantanée hors ligne ne sera pas disponible pour les expéditeurs s'ils disposent d'une stratégie client qui désactive l'enregistrement automatique des messages hors ligne dans le dossier d'historique des conversations (EnableIMAutoArchiving = $false). Il n'existe aucun mécanisme permettant de vérifier si le destinataire est en mesure de recevoir les messages hors ligne.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-p103">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false). There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="0ecb3-120">Pour les messages hors connexion envoyés au sein de la même organisation, ils sont reçus sous la forme d’un message électronique avec une classe de message instantané. Remarque. MissedConversation et sera inclus dans le dossier des **conversations manquées** d’Outlook, ainsi que dans l’historique des conversations qui sera sélectionné dans la boîte de message liste récente/historique des conversations dans les clients Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="0ecb3-121">Les messages hors ligne envoyés à partir d'une organisation fédérée seront reçus sous forme d'e-mail sans IM.Note.MisssedConversation et ne seront pas récupérés dans les dossiers de conversation manquée ni d'historique des conversations.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="0ecb3-122">Identification et résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="0ecb3-122">Troubleshooting</span></span>

<span data-ttu-id="0ecb3-123">Le délai d’envoi d’un message hors connexion lors de la sélection et du traitement d’un message hors connexion est de deux minutes.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="0ecb3-124">Si les messages hors connexion ne peuvent pas être traités, ils s’affichent dans l’annuaire suivant:</span><span class="sxs-lookup"><span data-stu-id="0ecb3-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="0ecb3-125">Le journal ETL principal de Skype entreprise contient des informations sur le traitement des messages hors ligne et constitue votre meilleure source d’investigation et de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="0ecb3-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0ecb3-p105">Un problème lié à l'échec de l'envoi des messages hors ligne et au dossier Brouillons saturé de messages a été signalé. Ce problème survenait avec les boîtes aux lettres Exchange sur site et a été résolu dans tous les canaux C2R depuis le 14/06/2016. </span><span class="sxs-lookup"><span data-stu-id="0ecb3-p105">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages. This occurred with Exchange On-Premises mailboxes. The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
