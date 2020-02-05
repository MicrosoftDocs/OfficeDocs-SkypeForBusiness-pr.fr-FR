---
title: Installation et test de Skype Entreprise pour Windows Phone
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Résumé : Découvrez comment installer et tester Skype entreprise sur votre Windows Phone.'
ms.openlocfilehash: 63d766a566f131bc58540a13e2a19aa2add0700b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768587"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Skype Entreprise Server 2015 : installation et test de Skype Entreprise pour Windows Phone
 
**Résumé :** Découvrez comment installer et tester Skype entreprise sur votre Windows Phone.
  
L’application Skype entreprise pour Windows Phone permet de bénéficier de la présence, de la messagerie instantanée (mi) et des appels audio et vidéo de Skype entreprise sur les appareils Windows Mobile. Les utilisateurs de Lync 2013 obtiendront l’application mise à jour automatiquement ou seront invités à faire la mise à jour manuellement, selon leurs paramètres utilisateur. Les nouveaux utilisateurs peuvent le télécharger à partir de [Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901). L’application Skype entreprise pour Windows Phone est uniquement disponible sur Windows Phone 8,1 et versions ultérieures.
  
Avant de diriger les utilisateurs de votre organisation à télécharger l’application, vous devez exécuter les tests suivants pour vérifier qu’ils sont correctement intégrés à votre environnement. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Installation de Skype entreprise Windows Phone 8,1

1. Accédez à [Windows Phone 8 Update central](https://www.windowsphone.com/en-us/how-to/wp8/update-central) pour mettre à jour votre téléphone vers windows Phone 8,1.
    
2. Depuis votre téléphone, accédez au **Store**, puis recherchez **Skype entreprise**.
    
3. Appuyez sur **Installer**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Première connexion à Skype Entreprise

1. Dans l’écran d' **Accueil** , balayez vers la gauche pour afficher vos applications installées, recherchez Skype entreprise pour Windows Phone, puis appuyez sur l’icône pour ouvrir l’application.
    
2. Entrez votre adresse de connexion (par exemple, user@domain.com) et votre mot de passe, puis appuyez sur **Terminer**.
    
     Votre nom d’utilisateur et votre adresse de connexion peuvent vous être demandés. Le nom d’utilisateur est celui que vous utilisez pour vous connecter au réseau de votre organisation, user@domain.com ou domaine\nomutilisateur..
    
3. Dans l’écran **Programme d’amélioration du produit**, appuyez sur **Participer** pour envoyer des données anonymes sur les problèmes et l’utilisation de l’application à Microsoft ou sur **Non merci** si vous préférez ne pas participer.
    
4. Dans l’écran **Ne manquez jamais vos appels professionnels**, entrez votre numéro de téléphone avec les indicatifs du pays et de la région. Lorsque Skype entreprise pour Windows Phone ne peut pas utiliser un réseau Wi-Fi ou un réseau de données cellulaires pour effectuer un appel audio ou vidéo, vous êtes automatiquement appelé à ce numéro et vous êtes connecté à la partie audio de l’appel.
    
5. Appuyez sur **suivant** et passez en revue les paramètres de notification et d’accès au répertoire :
    
   - **Notifications de transmission** Recevez une alerte lorsque vous recevez un nouveau message instantané ou un nouvel appel. Cette option est **activée** par défaut (recommandé).
    
     > [!IMPORTANT]
     > Si vous désactivez ce paramètre, vous ne serez pas averti des messages instantanés, des appels ou des autres alertes Skype entreprise pour Windows Phone, sauf si l’application est active. 
  
   - **Autoriser l’accès au répertoire téléphonique** Recherchez des contacts sur votre téléphone mobile lorsque vous recherchez des contacts dans Skype entreprise pour Windows Phone.
    
6. Appuyez sur **suivant** pour commencer à utiliser Skype entreprise pour Windows Phone.
    
    [Vous avez besoin d’aide pour vous connecter ?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Vérification de l’installation du client mobile

Après avoir configuré le client et que vous êtes connecté avec succès, utilisez les tests suivants pour vérifier que votre installation de Skype entreprise pour Windows Phone fonctionne correctement sur votre appareil mobile.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Recherche d’un contact dans l’annuaire d’entreprise

1. Dans la liste des contacts, appuyez sur **Rechercher**.
    
2. Recherchez un contact qui n’existe que dans la liste d’adresses globale.
    
3. Vérifiez que le nom du contact figure dans les résultats de la recherche.
    
### <a name="test-instant-messaging-and-presence"></a>Test de la messagerie instantanée et de la présence

1. Dans la liste Contacts, tapez sur un contact.
    
2. Dans la carte de visite, appuyez sur la messagerie instantanée. ![Icône de messagerie instantanée dans Skype Entreprise](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)icône.
    
3. Vérifiez qu’une fenêtre de messagerie instantanée s’affiche et que vous pouvez taper et envoyer un message instantané.
    
### <a name="test-dial-out-conferencing"></a>Test de la conférence rendez-vous

1. Dans Outlook, planifiez une réunion Skype entreprise.
    
2. Sur votre Windows Phone, ouvrez l’invitation à la réunion.
    
3. Cliquez sur le lien dans la réunion afin de la rejoindre.
    
4. Répondez à l’appel du service de conférence et vérifiez que vous êtes connecté au système audio de la réunion.
    
### <a name="test-push-notifications"></a>Test des notifications Push

1. Sélectionnez deux comptes d’utilisateurs différents pour ce test. 
    
2. Sur la fenêtre Windows Phone de l’utilisateur, connectez-vous à Skype entreprise pour Windows Phone avec le compte de l’utilisateur A.
    
3. Ouvrez une autre application sur l’appareil.
    
4. Sur un autre client, comme le client de bureau, connectez-vous à Skype entreprise avec le compte de l’utilisateur B.
    
5. Envoyez un message instantané de l’utilisateur B à l’utilisateur A.
    
6. Vérifiez que la notification de message instantané apparaît sur l’appareil mobile de l’utilisateur.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Supprimer Skype entreprise de votre Windows Phone

Pour supprimer l’application Skype entreprise pour Windows Phone de votre appareil mobile, procédez comme suit : 
  
1. Dans l’écran d’accueil, faites glisser votre doigt pour afficher la liste des applications. 
    
2. Appuyez de façon prolongée sur l’application Skype entreprise pour Windows Phone, puis cliquez sur **désinstaller**.
    


