---
title: Installer et tester les Skype Entreprise pour Windows Phone
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
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Résumé : Découvrez comment installer et tester des Skype Entreprise sur votre Windows Phone.'
ms.openlocfilehash: 49ba719f13edfa2d9dc85d00c71c59dc5b19b8d8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843537"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Installer et tester les Skype Entreprise pour Windows Phone
 
**Résumé :** Découvrez comment installer et tester des Skype Entreprise sur votre Windows Phone.
  
L Skype Entreprise pour Windows Phone applance Skype Entreprise la présence, la messagerie instantanée et les appels vocaux et vidéo Windows appareils mobiles. Les utilisateurs lync 2013 obtiennent automatiquement l’application mise à jour ou sont invités à la mettre à jour manuellement, en fonction de leurs paramètres utilisateur. Les nouveaux utilisateurs peuvent le télécharger à partir [Windows Phone Marketplace.](https://go.microsoft.com/fwlink/p/?linkid=231901) L Skype Entreprise pour Windows Phone est disponible uniquement sur Windows Phone 8.1 et ultérieures.
  
Avant d’orienter les utilisateurs de votre organisation vers le téléchargement de l’application, vous devez exécuter les tests suivants pour vous assurer qu’elle est correctement intégrée à votre environnement. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Installer Skype Entreprise Windows Phone 8.1

1. Accédez [au Windows Phone 8 central](https://www.windowsphone.com/en-us/how-to/wp8/update-central) pour mettre à jour votre téléphone vers Windows Phone 8.1.
    
2. À partir de votre téléphone, allez dans le **Store** et recherchez **Skype Entreprise**.
    
3. Appuyez **sur Installer.** 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Connectez-vous Skype Entreprise pour la première fois

1. Sur **l’écran** d’accueil, balayez vers la gauche pour afficher vos applications installées, recherchez Skype Entreprise pour Windows Phone, puis appuyez sur l’icône pour ouvrir l’application.
    
2. Entrez votre adresse de signature (par exemple, user@domain.com) et votre mot de passe, puis appuyez sur **Terminé**.
    
     Votre nom d’utilisateur et une adresse de connexion peuvent vous être demandés. Le nom d’utilisateur est ce que vous utilisez pour vous connectez au réseau de votre organisation, qu’il s’user@domain.com ou domaine \nom d’utilisateur.
    
3. Dans **l’écran** Programme d’amélioration du produit, appuyez sur Rejoindre  pour envoyer des données anonymes sur les problèmes d’application et l’utilisation à Microsoft, ou Non merci si vous préférez ne pas participer. 
    
4. Dans **l’écran Ne manquez pas vos appels de** travail, entrez votre numéro de téléphone mobile avec des codes de pays et de région. Lorsque Skype Entreprise pour Windows Phone ne peut pas utiliser un réseau de données Wi-Fi ou cellulaire pour effectuer un appel audio ou vidéo, vous êtes automatiquement appelé à ce numéro et connecté à la partie audio de l’appel.
    
5. Appuyez **sur Suivant** et examinez les paramètres d’accès de notification et de phonébook :
    
   - **Notifications Push** Recevez une alerte lorsque vous recevez un nouveau messagerie instantanée ou un nouvel appel. Normalement **on** (recommandé).
    
     > [!IMPORTANT]
     > Si vous activez ce paramètre, vous n’êtes pas averti des E-S, des appels ou d’autres Skype Entreprise pour Windows Phone de messagerie unifiée, sauf si l’application est active. 
  
   - **Autoriser l’accès aux phonébooks** Recherchez des contacts sur votre téléphone mobile lorsque vous recherchez des contacts dans Skype Entreprise pour Windows Phone.
    
6. Appuyez **sur Suivant** pour commencer à utiliser Skype Entreprise pour Windows Phone.
    
    [Vous avez besoin d'aide pour vous connecter ?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Vérifier l’installation du client mobile

Après avoir configuré le client et vous être connecté, utilisez les tests suivants pour vérifier que votre installation de Skype Entreprise pour Windows Phone fonctionne correctement sur votre appareil mobile.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Rechercher un contact dans l’annuaire d’entreprise

1. Dans la liste contacts, appuyez sur **Rechercher.**
    
2. Recherchez un contact qui n’existe que dans la liste d’adresses globale.
    
3. Vérifiez que le nom du contact figure dans les résultats de la recherche.
    
### <a name="test-instant-messaging-and-presence"></a>Tester la messagerie instantanée et la présence

1. Dans la liste Contacts, tapez sur un contact.
    
2. Dans la carte de visite, appuyez sur la messagerie instantanée ![Icône pour la messagerie instantanée dans Skype Entreprise.](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png).
    
3. Vérifiez qu’une fenêtre de messagerie instantanée s’affiche et que vous pouvez taper et envoyer un message instantané.
    
### <a name="test-dial-out-conferencing"></a>Tester la conférence rendez-vous

1. Dans Outlook, planifier une Skype Entreprise réunion.
    
2. Sur votre Windows Phone, ouvrez l’invitation à la réunion.
    
3. Cliquez sur le lien dans la réunion afin de la rejoindre.
    
4. Répondez à l’appel du service de conférence et vérifiez que vous êtes connecté au système audio de la réunion.
    
### <a name="test-push-notifications"></a>Tester les notifications de type push

1. Sélectionnez deux comptes d’utilisateur différents pour ce test. 
    
2. Sur le compte de l’Windows Phone, connectez-vous Skype Entreprise pour Windows Phone compte de l’utilisateur A.
    
3. Ouvrez une autre application sur l’appareil.
    
4. Sur un autre client, tel que le client de bureau, connectez-vous Skype Entreprise compte de l’utilisateur B.
    
5. Envoyez un message instantané de l’utilisateur B à l’utilisateur A.
    
6. Vérifiez que la notification de messagerie instantanée s’affiche sur l’appareil mobile de l’utilisateur A.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Supprimez Skype Entreprise de votre Windows Phone

Pour supprimer l’Skype Entreprise pour Windows Phone de votre appareil mobile : 
  
1. À partir de l’écran d’accueil, effectuez un balayage pour voir la liste des applications. 
    
2. Appuyez et maintenez la Skype Entreprise pour Windows Phone application, puis sélectionnez **Désinstaller.**
    


