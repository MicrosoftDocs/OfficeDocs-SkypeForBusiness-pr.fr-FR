---
title: Utilisation de l’authentification à deux facteurs avec le client Skype Entreprise et Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Résumé : Utilisez l’authentification à deux facteurs avec Skype pour Business Server 2015 et Skype pour les entreprises.'
ms.openlocfilehash: 6bb2133533b640cd573730ca608f5845164ea282
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server-2015"></a>Utilisation de l’authentification à deux facteurs avec le client Skype Entreprise et Skype Entreprise Server 2015
 
**Résumé :** Utiliser l’authentification à deux facteurs avec Skype pour Business Server 2015 et Skype pour les entreprises.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Première connexion à Skype Entreprise

Vos informations de connexion sont généralement configurées automatiquement lors de l’installation de Skype pour les entreprises. Mais vous utilisez Skype pour les entreprises, la première fois que vous devrez démarrer manuellement le client.
  
### <a name="to-sign-in-for-the-first-time"></a>Pour se connecter pour la première fois

1. Ouvrez une session sur le réseau de votre organisation.
    
2. Sélectionnez **Démarrer** > **tous les programmes** > **Skype pour les entreprises**.
    
    L’écran de connexion doit s’afficher.
    
    - Si la zone Adresse de connexion est déjà renseignée, vérifiez que l’adresse affichée est correcte.
    
    - S’il n’est pas correct, ou si la zone est vide, entrez votre adresse de connexion (qui est généralement le même que votre adresse de courriel).
    
    - Si la zone Mot de passe qui s’affiche n’est pas renseignée, ajoutez votre mot de passe.
    
3. Sélectionnez **Se connecter**.
    
## <a name="sign-out-of-skype-for-business"></a>Déconnexion de Skype Entreprise

Lorsque vous avez terminé d’utiliser Skype pour les entreprises, vous pouvez fermer l’affichage, se déconnecter de votre session, ou quitter le programme, à partir du menu fichier. Le tableau ci-dessous explique les différences entre ces trois options :
  
|**Option**|**Ce qu’il fait**|**Comment effectuer**|
|:-----|:-----|:-----|
|Fermer  <br/> |Ferme l’affichage, mais vous permet du Skype pour session Business identifiée avec votre utilisateur ID de continuer à s’exécuter. Cela vous permet de continuer à recevoir des notifications et à interagir avec d’autres personnes. <br/> <br/> Vous pouvez obtenir l’affichage précédent à tout moment en cliquant sur le Skype pour entreprise icône sur la barre des tâches ou dans la zone de notification au bas de votre écran.  <br/> | Dans la fenêtre principale de Business Skype, effectuez une des opérations suivantes : <br/> 1. Cliquez sur le bouton **Options** , puis sélectionnez le **fichier** > **Fermer**.  <br/> 2. Cliquez sur le bouton **Fermer** (X) dans le coin supérieur droit de la fenêtre. <br/> |
|Se déconnecter  <br/> |Fin de la session associée à votre nom d’utilisateur, mais Skype pour entreprise continue à s’exécuter en arrière-plan. Lorsque vous vous déconnectez, la fenêtre de connexion s’affiche.  <br/> **Conseil :** Sélectionnez **Supprimer de mes informations de connexion** lorsque vous vous déconnectez de supprimer l’enregistrement de votre nom d’utilisateur et le mot de passe de l’ordinateur. Cela permet au support technique de résoudre plus facilement les problèmes de connexion. Vos informations de connexion sont mieux sécurisées, car l’ouverture de session avec vos informations d’identification est plus difficile pour des utilisateurs non autorisés. <br/> |Dans la fenêtre principale de Business Skype, cliquez sur le bouton **Options** , puis sélectionnez **fichier** > **Déconnexion**.  <br/> |
|Quitter  <br/> |Termine votre Skype pour la session de l’entreprise et s’arrête à Skype pour entreprises sur votre ordinateur. Après avoir quitté, si vous souhaitez redémarrer, sélectionnez **Démarrer** > **Tous les programmes** > Skype pour les entreprises. <br/> |Dans la fenêtre principale de Business Skype, cliquez sur le bouton **Options** , puis sélectionnez **fichier** > **Exit**.  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Connexion à Skype Entreprise avec une carte à puce

Certaines organisations utilisent désormais une procédure de connexion en plusieurs étapes appelée « authentification à deux facteurs » pour renforcer la sécurité de leurs utilisateurs. Si vous avez prévu d’utiliser cette option, vous aurez besoin d’une « carte à puce » pour vous connecter sur Skype pour les entreprises. Les cartes à puce peuvent être physiques ou virtuels :
  
- **Physique** La taille d’une carte de crédit. Insérer dans un lecteur de carte à puce lors de la connexion.
    
- **Virtuel** Pas un objet physique, mais un identificateur électronique écrite sur une puce spéciale sur votre ordinateur, ce qui génère essentiellement de la carte à puce dans votre ordinateur. Disponible uniquement pour une utilisation avec les ordinateurs Windows 8 contenant la puce TPM (Trusted Platform Module).
    
### <a name="enroll-your-smart-card"></a>Inscription de votre carte à puce

Avant de signer avec une carte à puce, la carte doit être « inscrit » — c'est-à-dire, vos informations d’identification de l’utilisateur doivent être identifié grâce à la carte. C’est le cas si la carte est physique ou virtuel. Ce processus peut déjà été effectués par votre Skype pour l’administrateur d’entreprise serveur 2015. Si vous n’êtes pas sûr si cela a été fait, vérifiez avec lui.
  
> [!NOTE]
> Dans la mesure où chaque carte virtuelle est associé uniquement à l’équipement qu’il est installé sur, une carte distincte devra être inscrits pour chaque ordinateur Windows 8 que vous utilisez. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Pour inscrire manuellement votre carte à puce

1. Ouvrez une session sur l’ordinateur que vous allez exécuter Skype pour entreprise sur.
    
2. À l’aide d’Internet Explorer, accédez à la page d’inscription de l’autorité de certificat via le Web de votre organisation. 
    
    Demandez à votre Skype pour l’administrateur du serveur de l’entreprise pour l’adresse web de cette ressource si vous ne l’avez déjà pas. L’URL doit ressembler à ceci : https://MyCA. [yourcompanyname] .com/certsrv.
    
    > [!NOTE]
    > Si vous utilisez Internet Explorer 10, vous devrez consulter ce site Web en Mode de compatibilité. 
  
3. Lorsque vous êtes invité à ouvrir une session sur la page de certification, ouvrez une session en utilisant votre compte de domaine (et non en tant qu’administrateur de votre ordinateur).
    
4. Dans la page d’accueil du site web, sélectionnez **Demander un certificat**.
    
5. Sélectionnez **Demande avancée**.
    
6. Sélectionnez **Créer et envoyer une demande auprès de cette autorité de certification**, puis cliquez sur **Suivant**.
    
7. Désormais, vous verrez une page appelée Station d’inscription de carte à puce. Acceptez la demande d’installation du contrôle ActiveX, puis renseignez les champs de l’écran Demande de certificat avancée, comme suit :
    
    a. Sélectionnez **Utilisateur de carte à puce** dans la liste déroulante **Modèle de certificat**.
    
    b. Sélectionnez **Créer un jeu de clés**.
    
    c. Recherchez les informations relatives au fabricant sur l’étiquette de votre carte à puce, puis sélectionnez le fabricant dans la liste déroulante **Fournisseur de services de chiffrement**.
    
    d. Sélectionnez **fournisseur de services cryptographiques** comme le Format de la demande, s’il n’est pas déjà sélectionné.
    
    e. Sélectionnez **sha1** à partir de la liste déroulante algorithme de hachage, s’il n’est pas déjà sélectionné.
    
    f. Nommez votre certificat vous reconnaît et cliquez sur **Envoyer**.
    
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

Avant d’utiliser votre carte à puce pour la première fois, il est recommandé de cliquer sur **Supprimer mes informations de connexion** sur le Skype pour entreprise-page de connexion. Cela permet de supprimer les informations d’identification de connexion stockées sur votre ordinateur et d’éliminer une source possible d’erreur.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Pour vous connecter à Skype Entreprise avec vos informations d’identification de carte à puce

1. Démarrer le Skype pour client d’entreprise.
    
2. Dans l’écran Se connecter, tapez le nom de compte d’utilisateur de connexion dans la zone **Adresse de connexion**, puis cliquez sur **Se connecter**.
    
3. Si vous utilisez une carte à puce virtuelle, ignorez cette étape.
    
    Si vous utilisez une carte à puce physique, insérez la carte à puce dans le lecteur de cartes à puce, puis, lorsque vous y êtes invité, cliquez sur **OK** lorsque la carte est détectée.
    
4. Tapez le code confidentiel de votre carte à puce, puis cliquez sur **OK**.
    
    > [!NOTE]
    > Si le support technique ne vous a pas communiqué de code confidentiel, utilisez la valeur par défaut (12345678). 
  
## <a name="see-also"></a>Voir aussi

#### 

[Gérer l’authentification à deux facteurs dans Skype pour Business Server 2015](two-factor-authentication.md)
  
[Configurer l’authentification à deux facteurs dans Skype pour Business Server 2015](configure.md)

