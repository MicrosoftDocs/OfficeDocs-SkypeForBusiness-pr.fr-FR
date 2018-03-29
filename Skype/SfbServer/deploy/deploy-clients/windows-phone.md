---
title: Installation et test de Skype Entreprise pour Windows Phone
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Résumé : Apprenez à installer et tester Skype pour le commerce sur votre Windows Phone.'
ms.openlocfilehash: c3f9fcf20726c4fd33dc4de462b64a1397373a0f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Skype Entreprise Server 2015 : installation et test de Skype Entreprise pour Windows Phone
 
**Résumé :** Apprenez à installer et tester Skype pour le commerce sur votre Windows Phone.
  
Le Skype pour l’application d’entreprise pour Windows Phone apporte Skype pour entreprise présence, messagerie instantanée (MI) et appel vocal et vidéo pour les périphériques Windows mobile. Les utilisateurs de Lync 2013 obtiendront l’application mise à jour automatiquement ou seront invités à faire la mise à jour manuellement, selon leurs paramètres utilisateur. Nouveaux utilisateurs peuvent le télécharger à partir du [Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901). Le Skype pour l’application d’entreprise pour Windows Phone est disponible uniquement sur Windows Phone 8.1 et versions ultérieures.
  
Avant de diriger les utilisateurs de votre organisation pour télécharger l’application, vous voudrez exécuter les tests suivants pour vous assurer qu’il est correctement intégrée dans votre environnement. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Installation de Skype pour Windows Phone de Business 8.1

1. Accédez à [Windows Phone 8 jour central](https://www.windowsphone.com/en-us/how-to/wp8/update-central) pour mettre à jour votre téléphone à 8.1 de Windows Phone.
    
2. À partir de votre téléphone, accéder à la **banque**et rechercher **Skype pour les entreprises**.
    
3. Appuyez sur **Installer**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Première connexion à Skype Entreprise

1. Sur l’écran de **démarrage** , passage de gauche pour afficher vos applications installées, recherchez Skype pour Business pour Windows Phone et puis cliquez sur l’icône pour ouvrir l’application.
    
2. Entrez votre adresse de connexion (par exemple, user@domain.com) et le mot de passe et appuyez sur **terminé**.
    
     Votre nom d’utilisateur et votre adresse de connexion peuvent vous être demandés. Le nom d’utilisateur est ce qui vous permet de vous connecter au réseau de votre organisation, soit user@domain.com ou Domaine\NomUtilisateur.
    
3. Dans l’écran **Programme d’amélioration du produit**, appuyez sur **Participer** pour envoyer des données anonymes sur les problèmes et l’utilisation de l’application à Microsoft ou sur **Non merci** si vous préférez ne pas participer.
    
4. Dans l’écran **Ne manquez jamais vos appels professionnels**, entrez votre numéro de téléphone avec les indicatifs du pays et de la région. Lorsque Skype pour Business pour Windows Phone ne peut pas utiliser un Wi-Fi ou le réseau de données cellulaires pour effectuer un appel audio ou vidéo, automatiquement appelé à ce numéro et vous connecté à la partie audio de l’appel.
    
5. Cliquez sur **suivant** et passez en revue la notification et les paramètres d’accès de l’annuaire :
    
  - **Notifications de transmission** Obtention d’une alerte lorsque vous recevez un appel ou messagerie instantanée de nouveau. Cette option est **activée** par défaut (recommandé).
    
    > [!IMPORTANT]
    > Si vous activez ce paramètre, vous ne serez pas averti d’IMs, les appels ou autre Skype pour les alertes d’entreprise pour Windows Phone, sauf si l’application est active. 
  
  - **Autoriser les accès de l’annuaire** Rechercher des contacts sur votre téléphone mobile lorsque vous recherchez des contacts dans Skype Business pour Windows Phone.
    
6. Cliquez sur **suivant** pour commencer à utiliser Skype pour Business pour Windows Phone.
    
    [Vous avez besoin d’aide pour vous connecter ?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Vérification de l’installation du client mobile

Après avoir configuré le client et que vous parvenez à vous, effectuez les tests suivants pour vérifier que votre installation de Skype pour Business pour Windows Phone fonctionne correctement sur votre appareil mobile.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Recherche d’un contact dans l’annuaire d’entreprise

1. Dans la liste des contacts, appuyez sur **Rechercher**.
    
2. Recherchez un contact qui n’existe que dans la liste d’adresses globale.
    
3. Vérifiez que le nom du contact figure dans les résultats de la recherche.
    
### <a name="test-instant-messaging-and-presence"></a>Test de la messagerie instantanée et de la présence

1. Dans la liste Contacts, tapez sur un contact.
    
2. Dans la fiche contact, cliquez sur la messagerie instantanée (MI) ![Icône de messagerie instantanée dans Skype Entreprise](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)icône.
    
3. Vérifiez qu’une fenêtre de messagerie instantanée s’affiche et que vous pouvez taper et envoyer un message instantané.
    
### <a name="test-dial-out-conferencing"></a>Test de la conférence rendez-vous

1. Dans Outlook, planifiez un Skype pour une réunion d’affaires.
    
2. Sur votre Windows Phone, ouvrez l’invitation à la réunion.
    
3. Cliquez sur le lien dans la réunion afin de la rejoindre.
    
4. Répondez à l’appel du service de conférence et vérifiez que vous êtes connecté au système audio de la réunion.
    
### <a name="test-push-notifications"></a>Test des notifications Push

1. Sélectionnez deux comptes d’utilisateurs différents pour ce test. 
    
2. Sur Windows Phone de l’utilisateur A, connectez-vous à Skype pour Business pour Windows Phone avec le compte de l’utilisateur A.
    
3. Ouvrez une autre application sur l’appareil.
    
4. Sur un autre client, tel que le client de bureau, connectez-vous à Skype pour entreprises avec le compte de l’utilisateur B.
    
5. Envoyez un message instantané de l’utilisateur B à l’utilisateur A.
    
6. Vérifiez que la notification de la messagerie instantanée s’affiche sur le périphérique mobile de l’utilisateur A.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Retirez votre Windows Phone de Skype pour entreprise

Pour supprimer le Skype pour l’application d’entreprise pour Windows Phone de votre appareil mobile : 
  
1. Dans l’écran d’accueil, faites glisser votre doigt pour afficher la liste des applications. 
    
2. Appuyez sur et maintenez la Skype pour application d’entreprise pour Windows Phone puis sélectionnez **désinstaller**.
    
## <a name="see-also"></a>Voir aussi

#### 


[Mise en route avec Skype pour Business pour Windows Phone 8.1]()

