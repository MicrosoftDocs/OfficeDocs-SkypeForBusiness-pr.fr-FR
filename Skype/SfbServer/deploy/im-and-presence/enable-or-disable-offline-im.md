---
title: Activer ou désactiver la messagerie instantanée hors connexion dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Découvrez comment activer ou désactiver la messagerie instantanée hors connexion dans Skype Entreprise Server.
ms.openlocfilehash: 510ebe65e60b9ea12d2f368b0e2d33c705b8d0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801944"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="69f25-103">Activer ou désactiver la messagerie instantanée hors connexion dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="69f25-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="69f25-104">Découvrez comment activer ou désactiver la messagerie instantanée hors connexion dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="69f25-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="69f25-105">Activer la messagerie instantanée hors connexion dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="69f25-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="69f25-106">La messagerie instantanée hors connexion est une fonctionnalité côté client intégrée au client Skype Entreprise (version 2016 C2R 16.0.6701.1000 ou supérieure) qui tire parti des services web Exchange (EWS) pour envoyer des messages du client Skype Entreprise vers la boîte aux lettres Exchange d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="69f25-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="69f25-107">La messagerie instantanée hors connexion utilise les services web Exchange (EWS) pour envoyer des messages hors connexion du client Skype Entreprise à la boîte aux lettres du destinataire.</span><span class="sxs-lookup"><span data-stu-id="69f25-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="69f25-108">EWS doit être disponible pour le client Skype Entreprise pour que les messages hors connexion soient envoyés.</span><span class="sxs-lookup"><span data-stu-id="69f25-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="69f25-109">Pour en savoir plus sur la planification de la messagerie instantanée et de la présence, voir Planifier la messagerie instantanée et [la présence dans Skype Entreprise Server.](../../plan-your-deployment/instant-messaging-and-presence.md)</span><span class="sxs-lookup"><span data-stu-id="69f25-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="69f25-110">Si la boîte aux lettres de l’utilisateur est hébergée dans Exchange local, le client Skype Entreprise (2016 C2R build 16.0.6920.1000) est requis.</span><span class="sxs-lookup"><span data-stu-id="69f25-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="69f25-111">Pour activer ou désactiver la messagerie instantanée hors connexion dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="69f25-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="69f25-112">Ouvrez Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="69f25-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="69f25-113">Exécutez la commande suivante pour activer la messagerie instantanée hors connexion.</span><span class="sxs-lookup"><span data-stu-id="69f25-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="69f25-114">Dans Skype Entreprise Server 2015 CU3, l’option EnableOfflineIM est définie sur $True par défaut.</span><span class="sxs-lookup"><span data-stu-id="69f25-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="69f25-115">Pour désactiver, définissez cette valeur sur $False.</span><span class="sxs-lookup"><span data-stu-id="69f25-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="69f25-116">Exécutez la commande suivante pour confirmer que la possibilité de stocker des messageries instantanées hors connexion est définie.</span><span class="sxs-lookup"><span data-stu-id="69f25-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="69f25-117">Intégration de la messagerie instantanée hors connexion à Exchange</span><span class="sxs-lookup"><span data-stu-id="69f25-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="69f25-118">La messagerie instantanée hors connexion ne sera pas disponible pour les expéditeurs s’ils disposent d’une stratégie de client qui désactive l’enregistrement automatique des messages hors connexion dans le dossier d’historique des conversations (EnableIMAutoArchiving = $false).</span><span class="sxs-lookup"><span data-stu-id="69f25-118">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false).</span></span> <span data-ttu-id="69f25-119">Il n’existe aucun mécanisme permettant de vérifier si le destinataire est en mesure de recevoir des messages hors connexion.</span><span class="sxs-lookup"><span data-stu-id="69f25-119">There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="69f25-120">Pour les messages hors connexion envoyés au sein de la même organisation, ils sont reçus en tant que messages électroniques avec la classe de message IM.Note.MissedConversation et sont inclus dans le dossier Conversation manquée **Outlook,** ainsi que dans l’historique des conversations qui sera repris dans l’onglet Liste récente/Historique des conversations dans les clients Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="69f25-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="69f25-121">Pour les messages hors connexion envoyés à partir d’une organisation fédérée, ils sont reçus en tant que messages électroniques sans IM.Note.MisssedConversation et ne sont pas pris en compte dans les dossiers de conversation manquée ou d’historique des conversations.</span><span class="sxs-lookup"><span data-stu-id="69f25-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="69f25-122">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="69f25-122">Troubleshooting</span></span>

<span data-ttu-id="69f25-123">Il existe un minuteur de deux minutes entre le moment où un message hors connexion est envoyé et le moment où il est choisi et traitée.</span><span class="sxs-lookup"><span data-stu-id="69f25-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="69f25-124">Si les messages hors connexion ne peuvent pas être traitées, ils apparaissent dans le répertoire suivant :</span><span class="sxs-lookup"><span data-stu-id="69f25-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="69f25-125">Le journal ETL Skype Entreprise principal contient des informations sur le traitement des messages hors connexion et constitue la meilleure source d’investigation/de dépannage.</span><span class="sxs-lookup"><span data-stu-id="69f25-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="69f25-126">Un problème a été signalé lorsque les messages hors connexion n’ont pas pu être envoyés et que le dossier « Brouillons » était rempli de messages.</span><span class="sxs-lookup"><span data-stu-id="69f25-126">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages.</span></span> <span data-ttu-id="69f25-127">Cela s’est produit avec les boîtes aux lettres Exchange sur site.</span><span class="sxs-lookup"><span data-stu-id="69f25-127">This occurred with Exchange On-Premises mailboxes.</span></span> <span data-ttu-id="69f25-128">Le problème a été résolu dans tous les canaux C2R depuis le 14/06/2016.</span><span class="sxs-lookup"><span data-stu-id="69f25-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
