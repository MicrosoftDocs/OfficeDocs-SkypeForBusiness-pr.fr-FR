---
title: Installation et test de Skype Entreprise pour Windows Phone
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Résumé : Découvrez comment installer et tester Skype pour les entreprises sur votre Windows Phone.'
ms.openlocfilehash: 90e8b99532e51399f9f76e5e12d60a3eeab84481
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978046"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Skype Entreprise Server 2015 : installation et test de Skype Entreprise pour Windows Phone
 
**Résumé :** Découvrez comment installer et tester Skype pour les entreprises sur votre Windows Phone.
  
Le Skype pour application d’entreprise pour Windows Phone apporte Skype pour Business présence, messagerie instantanée (MI) et appel vocal et vidéo pour appareils Windows mobile. Les utilisateurs de Lync 2013 obtiendront l’application mise à jour automatiquement ou seront invités à faire la mise à jour manuellement, selon leurs paramètres utilisateur. Nouveaux utilisateurs peuvent télécharger à partir de [Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901). Le Skype pour application d’entreprise pour Windows Phone est disponible uniquement sur Windows Phone 8.1 et versions ultérieures.
  
Avant de diriger les utilisateurs dans votre organisation pour télécharger l’application, vous souhaiterez effectuer les tests suivants pour vous assurer qu’il est correctement intégrée dans votre environnement. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Installer Skype pour entreprise Windows Phone 8.1

1. Accédez à [Windows Phone 8 mettre à jour centrale](https://www.windowsphone.com/en-us/how-to/wp8/update-central) pour mettre à jour votre téléphone pour Windows Phone 8.1.
    
2. À partir de votre téléphone, accédez à la **banque**et recherchez **Skype pour les entreprises**.
    
3. Appuyez sur **Installer**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Première connexion à Skype Entreprise

1. Sur l’écran de **démarrage** , effectuez un balayage gauche pour afficher vos applications installées, rechercher Skype pour Business pour Windows Phone et puis cliquez sur l’icône pour ouvrir l’application.
    
2. Entrez votre adresse de connexion (par exemple, user@domain.com) et le mot de passe, puis cliquez sur **terminé**.
    
     Votre nom d’utilisateur et votre adresse de connexion peuvent vous être demandés. Le nom d’utilisateur est que vous utilisez pour vous connecter au réseau de votre organisation, user@domain.com ou DOMAINE\nom_utilisateur.
    
3. Dans l’écran **Programme d’amélioration du produit**, appuyez sur **Participer** pour envoyer des données anonymes sur les problèmes et l’utilisation de l’application à Microsoft ou sur **Non merci** si vous préférez ne pas participer.
    
4. Dans l’écran **Ne manquez jamais vos appels professionnels**, entrez votre numéro de téléphone avec les indicatifs du pays et de la région. Lorsque Skype pour Business pour Windows Phone ne peut pas utiliser un réseau de données cellulaires ou de Wi-Fi pour émettre un appel audio ou vidéo, vous être automatiquement appelé à ce numéro et connecté à la partie audio de l’appel.
    
5. Cliquez sur **suivant** et passez en revue la notification et les paramètres d’accès de l’annuaire :
    
  - **Notifications Push** Obtention d’une alerte lorsque vous recevez un appel ou un nouveau message. Cette option est **activée** par défaut (recommandé).
    
    > [!IMPORTANT]
    > Si vous activez ce paramètre, vous ne serez pas averti des messages instantanés, des appels ou autres Skype pour les alertes d’entreprise pour Windows Phone, sauf si l’application est active. 
  
  - **Autoriser l’accès annuaire** Rechercher des contacts sur votre téléphone mobile lorsque vous recherchez des contacts dans Skype Business pour Windows Phone.
    
6. Cliquez sur **suivant** pour commencer à utiliser Skype pour Business pour Windows Phone.
    
    [Besoin d’aide pour vous connecter ?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Vérification de l’installation du client mobile

Après avoir configuré le client et ouvert une session, utilisez les tests suivants pour vérifier que votre installation de Skype pour Business pour Windows Phone fonctionne correctement sur votre appareil mobile.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Recherche d’un contact dans l’annuaire d’entreprise

1. Dans la liste des contacts, appuyez sur **Rechercher**.
    
2. Recherchez un contact qui n’existe que dans la liste d’adresses globale.
    
3. Vérifiez que le nom du contact figure dans les résultats de la recherche.
    
### <a name="test-instant-messaging-and-presence"></a>Test de la messagerie instantanée et de la présence

1. Dans la liste Contacts, tapez sur un contact.
    
2. Dans la carte de visite, cliquez sur la messagerie instantanée (MI) ![Icône de messagerie instantanée dans Skype Entreprise](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)icône.
    
3. Vérifiez qu’une fenêtre de messagerie instantanée s’affiche et que vous pouvez taper et envoyer un message instantané.
    
### <a name="test-dial-out-conferencing"></a>Test de la conférence rendez-vous

1. Dans Outlook, planifiez une Skype pour une réunion d’affaires.
    
2. Sur votre Windows Phone, ouvrez l’invitation à la réunion.
    
3. Cliquez sur le lien dans la réunion afin de la rejoindre.
    
4. Répondez à l’appel du service de conférence et vérifiez que vous êtes connecté au système audio de la réunion.
    
### <a name="test-push-notifications"></a>Test des notifications Push

1. Sélectionnez deux comptes d’utilisateurs différents pour ce test. 
    
2. Sur Windows Phone de l’utilisateur A, connectez-vous à Skype pour Business pour Windows Phone avec le compte de l’utilisateur A.
    
3. Ouvrez une autre application sur l’appareil.
    
4. Sur un autre client, tel que le client de bureau, connectez-vous à Skype pour les entreprises avec le compte de l’utilisateur B.
    
5. Envoyez un message instantané de l’utilisateur B à l’utilisateur A.
    
6. Vérifiez que la notification de messagerie instantanée s’affiche sur l’appareil mobile de l’utilisateur A.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Supprimer votre Windows Phone de Skype pour les entreprises

Pour supprimer le Skype pour application d’entreprise pour Windows Phone à partir de votre appareil mobile : 
  
1. Dans l’écran d’accueil, faites glisser votre doigt pour afficher la liste des applications. 
    
2. Appuyez sur et maintenez le Skype pour application d’entreprise pour Windows Phone, puis sélectionnez **désinstaller**.
    


