---
title: Utiliser l’authentification à deux facteurs avec Skype pour client d’entreprise et Skype pour Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Résumé : Utilisez l’authentification à deux facteurs avec Skype pour Business Server et Skype pour les entreprises.'
ms.openlocfilehash: 95e44c50dec37eea86b90317575a09509df80649
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986550"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Utiliser l’authentification à deux facteurs avec Skype pour client d’entreprise et Skype pour Business Server
 
**Résumé :** Utiliser l’authentification à deux facteurs avec Skype pour Business Server et Skype pour les entreprises.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Première connexion à Skype Entreprise

Vos informations de connexion sont généralement configurées automatiquement lors de l’installation Skype pour les entreprises. Mais la première fois que vous utilisez Skype pour les entreprises, vous devrez démarrer manuellement le client.
  
### <a name="to-sign-in-for-the-first-time"></a>Pour se connecter pour la première fois

1. Connectez-vous au réseau de votre organisation.
    
2. Sélectionnez **Démarrer** > **tous les programmes** > **Skype pour les entreprises**.
    
    L’écran de connexion doit s’afficher.
    
    - Si la zone Adresse de connexion est déjà renseignée, vérifiez que l’adresse affichée est correcte.
    
    - S’il n’est pas correct, ou si la zone est vide, entrez votre adresse de connexion (qui est généralement identique à votre adresse de messagerie).
    
    - Si la zone Mot de passe qui s’affiche n’est pas renseignée, ajoutez votre mot de passe.
    
3. Sélectionnez **Se connecter**.
    
## <a name="sign-out-of-skype-for-business"></a>Déconnexion de Skype Entreprise

Lorsque vous avez terminé d’utiliser Skype pour les entreprises, vous pouvez fermer l’affichage, vous déconnecter de votre session ou quitter le programme, à partir du menu fichier. Le tableau ci-dessous explique les différences entre ces trois options :
  
|**Option**|**Action**|**Utilisation**|
|:-----|:-----|:-----|
|Fermer  <br/> |Ferme l’affichage, mais vous permet du Skype pour session Business identifiée par l’utilisateur de votre ID de continuer à exécuter. Cela vous permet de continuer à recevoir des notifications et à interagir avec d’autres personnes. <br/> <br/> Vous pouvez obtenir l’affichage précédent à tout moment en cliquant sur le Skype pour entreprise icône sur la barre des tâches ou de la zone de notification au bas de votre écran.  <br/> | Sur Skype pour la fenêtre principale d’entreprise, effectuez l’une des options suivantes : <br/> 1. Cliquez sur le bouton **Options** , puis sélectionnez le **fichier** > **Fermer**.  <br/> 2. Cliquez sur le bouton **Fermer** (X) dans le coin supérieur droit de la fenêtre. <br/> |
|Se déconnecter  <br/> |Se termine la session associée à votre nom d’utilisateur, mais Skype pour les entreprises se poursuit en arrière-plan. Lorsque vous vous déconnectez, la fenêtre de connexion s’affiche.  <br/> **Conseil :** Sélectionnez **Supprimer mes informations de connexion** lorsque vous vous déconnectez supprimer l’enregistrement de votre nom d’utilisateur et le mot de passe de l’ordinateur. Cela permet au support technique de résoudre plus facilement les problèmes de connexion. Vos informations de connexion sont mieux sécurisées, car l’ouverture de session avec vos informations d’identification est plus difficile pour des utilisateurs non autorisés. <br/> |Sur Skype pour la fenêtre principale d’entreprise, sélectionnez le bouton **Options** , puis sélectionnez le **fichier** > **Se déconnecter**.  <br/> |
|Quitter  <br/> |Met fin à votre Skype de session Business et Skype pour les entreprises s’arrête sur votre ordinateur. Après avoir quitté, si vous voulez redémarrer, sélectionnez **Démarrer** > **Tous les programmes** > Skype pour les entreprises. <br/> |Sur Skype pour la fenêtre principale d’entreprise, sélectionnez le bouton **Options** , puis sélectionnez le **fichier** > **Quitter**.  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Connexion à Skype Entreprise avec une carte à puce

Certaines organisations utilisent désormais une procédure de connexion en plusieurs étapes appelée « authentification à deux facteurs » pour renforcer la sécurité de leurs utilisateurs. Si vous avez prévu d’utiliser cette option, vous devez « carte à puce » pour vous connecter à Skype pour les entreprises. Les cartes à puce peut être physique ou virtuel :
  
- **Physique** À propos de la taille d’une carte de crédit. Insérer dans un lecteur de carte à puce lorsque vous vous connectez.
    
- **Virtuel** Pas d’un objet physique, mais un identificateur électronique écrite sur une puce spéciale sur votre ordinateur, ce qui génère essentiellement la carte à puce dans votre ordinateur. Disponible uniquement pour une utilisation avec les ordinateurs Windows 8 qui contiennent la puce TPM (Trusted Platform Module).
    
### <a name="enroll-your-smart-card"></a>Inscription de votre carte à puce

Avant que vous pouvez vous connecter avec une carte à puce, la carte doit être « inscrit » — autrement dit, vos informations d’identification de l’utilisateur doivent être identifiées avec la carte. C’est le cas si la carte est physique ou virtuel. Ce processus peut déjà été effectués par votre Skype pour l’administrateur du serveur d’entreprise. Si vous n’êtes pas certain que qui a été effectuée, vérifiez avec lui.
  
> [!NOTE]
> Étant donné que chaque carte à puce virtuel est associé uniquement à l’appareil il est installé, une autre carte devront être inscrits pour chaque ordinateur Windows 8 que vous utilisez. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Pour inscrire manuellement votre carte à puce

1. Ouvrez une session l’ordinateur que vous allez exécuter Skype pour les entreprises sur.
    
2. À l’aide d’Internet Explorer, accédez à la page d’inscription de l’autorité de certificat via le Web de votre organisation. 
    
    Demandez à votre Skype pour l’administrateur du serveur d’entreprise pour l’adresse web de cette ressource si vous ne l’avez déjà pas. L’URL doit ressembler à ceci : https://MyCA. [yourcompanyname] .com/certsrv.
    
    > [!NOTE]
    > Si vous utilisez Internet Explorer 10, vous devrez peut-être afficher ce site Web en Mode de compatibilité. 
  
3. Lorsque vous êtes invité à se connecter à la page de certification, ouvrez une session à l’aide de votre compte de domaine (et non en tant qu’administrateur de votre ordinateur).
    
4. Dans la page d’accueil du site web, sélectionnez **Demander un certificat**.
    
5. Sélectionnez **Demande avancée**.
    
6. Sélectionnez **Créer et envoyer une demande auprès de cette autorité de certification**, puis cliquez sur **Suivant**.
    
7. Vous allez maintenant voir une page appelée Station d’inscription de carte à puce. Acceptez la demande d’installation du contrôle ActiveX, puis renseignez les champs de l’écran Demande de certificat avancée, comme suit :
    
    a. Sélectionnez **Utilisateur de carte à puce** dans la liste déroulante **Modèle de certificat**.
    
    b. Sélectionnez **Créer un jeu de clés**.
    
    c. Recherchez les informations relatives au fabricant sur l’étiquette de votre carte à puce, puis sélectionnez le fabricant dans la liste déroulante **Fournisseur de services de chiffrement**.
    
    d. Sélectionnez **CSP** comme Format de demande, si elle n’est pas déjà sélectionnée.
    
    e. Sélectionnez **sha1** à partir de la liste déroulante de l’algorithme de hachage, s’il n’est pas déjà sélectionné.
    
    f. Nommez votre certificat que vous allez reconnaître, cliquez sur **Envoyer**.
    
8. Insérez votre carte à puce vierge dans le lecteur de cartes relié à la station d’inscription, puis cliquez sur **Inscrire**.
    
9. Lorsque vous y êtes invité, entrez votre code confidentiel, puis cliquez sur **OK**.
    
    > [!NOTE]
    > Si le support technique ne vous a pas communiqué de code confidentiel spécial pour inscrire votre carte à puce, utilisez la valeur de code confidentiel par défaut de la carte à puce (12345678). 
  
10. Sélectionnez l’option forçant l’utilisateur (vous) à modifier le code confidentiel à la première utilisation de la carte.
    
11. Insérez votre carte à puce vierge dans le lecteur de cartes relié à la station d’inscription, puis cliquez sur **Inscrire**.
    
12. Lorsque vous y êtes invité, entrez votre code confidentiel, puis cliquez sur **OK**.
    
    > [!NOTE]
    > Si le support technique ne vous a pas communiqué de code confidentiel spécial pour inscrire votre carte à puce, utilisez la valeur de code confidentiel par défaut de la carte à puce (12345678). 
  
13. Sélectionnez l’option forçant l’utilisateur (vous) à modifier le code confidentiel à la première utilisation de la carte.
    
14. Cliquez sur **OK** pour confirmer que le certificat affiché inclut vos informations.
    
15. Une fois que vous recevez l’avis confirmant l’émission du certificat, cliquez sur **Installer ce certificat** pour terminer la procédure d’inscription.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Connexion à Skype Entreprise avec vos informations d’identification de carte à puce

Avant d’utiliser votre carte à puce pour la première fois, il est recommandé que vous cliquez sur **Supprimer de mes informations de connexion** sur le Skype pour la page de connexion de l’entreprise. Cela permet de supprimer les informations d’identification de connexion stockées sur votre ordinateur et d’éliminer une source possible d’erreur.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Pour vous connecter à Skype Entreprise avec vos informations d’identification de carte à puce

1. Démarrez le Skype pour client d’entreprise.
    
2. Dans l’écran Se connecter, tapez le nom de compte d’utilisateur de connexion dans la zone **Adresse de connexion**, puis cliquez sur **Se connecter**.
    
3. Si vous utilisez une carte à puce virtuelle, ignorez cette étape.
    
    Si vous utilisez une carte à puce physique, insérez la carte à puce dans le lecteur de cartes à puce, puis, lorsque vous y êtes invité, cliquez sur **OK** lorsque la carte est détectée.
    
4. Tapez le code confidentiel de votre carte à puce, puis cliquez sur **OK**.
    
    > [!NOTE]
    > Si le support technique ne vous a pas communiqué de code confidentiel, utilisez la valeur par défaut (12345678). 
  
## <a name="see-also"></a>Voir aussi

[Gérer l’authentification à deux facteurs dans Skype pour Business Server](two-factor-authentication.md)
  
[Configurer l’authentification à deux facteurs Skype pour Business Server](configure.md)