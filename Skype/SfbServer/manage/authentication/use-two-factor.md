---
title: Utiliser l’authentification à deux facteurs avec le client Skype entreprise et Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Résumé: utilisez l’authentification à deux facteurs avec Skype entreprise Server et Skype entreprise.'
ms.openlocfilehash: 532e7567444b78dd30d053cf91aef1c10f0970bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286108"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Utiliser l’authentification à deux facteurs avec le client Skype entreprise et Skype entreprise Server
 
**Résumé:** Utiliser l’authentification à deux facteurs avec Skype entreprise Server et Skype entreprise.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Première connexion à Skype Entreprise

Vos informations de connexion sont généralement configurées automatiquement lors de l’installation de Skype entreprise. La première fois que vous utilisez Skype entreprise, vous devrez peut-être démarrer manuellement le client.
  
### <a name="to-sign-in-for-the-first-time"></a>Pour se connecter pour la première fois

1. Connectez-vous au réseau de votre organisation.
    
2. Sélectionnez **Démarrer** > **tous les programmes** > **Skype entreprise**.
    
    L’écran de connexion doit s’afficher.
    
    - Si la zone Adresse de connexion est déjà renseignée, vérifiez que l’adresse affichée est correcte.
    
    - Si ce n’est pas le cas, ou si la zone est vide, entrez votre adresse de connexion (il s’agit généralement de votre adresse de messagerie).
    
    - Si la zone Mot de passe qui s’affiche n’est pas renseignée, ajoutez votre mot de passe.
    
3. Sélectionnez **Se connecter**.
    
## <a name="sign-out-of-skype-for-business"></a>Déconnexion de Skype Entreprise

Lorsque vous avez fini d’utiliser Skype entreprise, vous pouvez fermer l’affichage, vous déconnecter de votre session ou quitter le programme à partir du menu fichier. Le tableau ci-dessous explique les différences entre ces trois options :
  
|**Option**|**Action**|**Utilisation**|
|:-----|:-----|:-----|
|Fermer  <br/> |Ferme votre affichage tout en permettant à la session Skype entreprise identifiée avec votre ID d’utilisateur de continuer à s’exécuter. Cela vous permet de continuer à recevoir des notifications et à interagir avec d’autres personnes. <br/> <br/> Vous pouvez récupérer l’affichage à tout moment en cliquant sur l’icône Skype entreprise dans la barre des tâches ou dans la zone de notification située en bas de votre écran.  <br/> | Dans la fenêtre principale de Skype entreprise, effectuez l’une des opérations suivantes: <br/> 1. Sélectionnez le **bouton Options** , puis cliquez sur**Fermer**le **fichier** > .  <br/> 2. cliquez sur le bouton **Fermer** (X) dans le coin supérieur droit de la fenêtre. <br/> |
|Se déconnecter  <br/> |Met fin à la session associée à votre ID d’utilisateur, mais Skype entreprise continue de s’exécuter en arrière-plan. Lorsque vous vous déconnectez, la fenêtre de connexion s’affiche.  <br/> **Astuce:** Si vous vous déconnectez, sélectionnez **Supprimer mes informations de connexion** pour supprimer l’enregistrement de votre ID de connexion et de votre mot de passe de votre ordinateur. Cela permet au support technique de résoudre plus facilement les problèmes de connexion. Vos informations de connexion sont mieux sécurisées, car l’ouverture de session avec vos informations d’identification est plus difficile pour des utilisateurs non autorisés. <br/> |Dans la fenêtre principale de Skype entreprise, cliquez sur le bouton **options** , puis **** > sélectionnez**se déconnecter**.  <br/> |
|Quitter  <br/> |Met fin à votre session Skype entreprise et arrête Skype entreprise sur votre ordinateur. Après avoir quitté le programme, si vous souhaitez redémarrer, sélectionnez **Démarrer** > **tous les programmes** > Skype entreprise. <br/> |Dans la fenêtre principale de Skype entreprise, sélectionnez le bouton **options** , puis sélectionnez **** > **quitter**.  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Connexion à Skype Entreprise avec une carte à puce

Certaines organisations utilisent désormais une procédure de connexion en plusieurs étapes appelée « authentification à deux facteurs » pour renforcer la sécurité de leurs utilisateurs. Si vous utilisez cette option, vous avez besoin d’une carte à puce pour vous connecter à Skype entreprise. Les cartes à puce peuvent être physiques ou virtuelles:
  
- **Physiques** À propos de la taille d’une carte de crédit. Vous l’insérez dans un lecteur de carte à puce lorsque vous vous connectez.
    
- **Virtuel** Il ne s’agit pas d’un objet physique, mais d’un identificateur électronique qui est écrit sur un processeur spécial sur votre ordinateur, qui, par essence, génère la carte à puce sur votre ordinateur. Disponible uniquement sur les ordinateurs Windows 8 qui contiennent le processeur TPM (Trusted Platform Module).
    
### <a name="enroll-your-smart-card"></a>Inscription de votre carte à puce

Pour que vous puissiez vous connecter à l’aide d’une carte à puce, celle-ci doit être «inscrite»; autrement dit, vos informations d’identification d’utilisateur doivent être identifiées sur la carte. C’est le cas, qu’il s’agisse d’une carte physique ou virtuelle. Ce processus a pu être déjà exécuté par votre administrateur Skype entreprise Server. Si vous ne savez pas si vous avez terminé, contactez-les.
  
> [!NOTE]
> Dans la mesure où chaque carte à puce virtuelle est associée uniquement à l’appareil sur lequel elle est installée, une carte séparée doit être inscrite pour chaque ordinateur Windows 8 que vous utilisez. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Pour inscrire manuellement votre carte à puce

1. Ouvrez une session sur l’ordinateur sur lequel vous exécutez Skype entreprise.
    
2. À l’aide d’Internet Explorer, accédez à la page d’inscription au Web de l’autorité de certification de votre organisation. 
    
    Si vous n’avez pas encore l’application, demandez à l’administrateur de votre serveur Skype entreprise d’obtenir l’adresse Web de cette ressource. L’URL ressemble à ceci: https://MyCA. [nom]. com/certsrv.
    
    > [!NOTE]
    > Si vous utilisez Internet Explorer 10, il est possible que vous deviez afficher ce site Web en mode de compatibilité. 
  
3. Lorsque vous êtes invité à vous connecter à la page de certification, connectez-vous en utilisant votre compte de domaine (plutôt que l’administrateur de votre ordinateur).
    
4. Dans la page d’accueil du site web, sélectionnez **Demander un certificat**.
    
5. Sélectionnez **Demande avancée**.
    
6. Sélectionnez **Créer et envoyer une demande auprès de cette autorité de certification**, puis cliquez sur **Suivant**.
    
7. Vous voyez à présent une page nommée station d’inscription de carte à puce. Acceptez la demande d’installation du contrôle ActiveX, puis renseignez les champs de l’écran Demande de certificat avancée, comme suit :
    
    a. Sélectionnez **Utilisateur de carte à puce** dans la liste déroulante **Modèle de certificat**.
    
    b. Sélectionnez **Créer un jeu de clés**.
    
    c. Recherchez les informations relatives au fabricant sur l’étiquette de votre carte à puce, puis sélectionnez le fabricant dans la liste déroulante **Fournisseur de services de chiffrement**.
    
    d. Sélectionnez **CSP** comme format de la requête, si ce n’est pas déjà fait.
    
    e. Sélectionnez **SHA1** dans la liste déroulante algorithme de hachage, si ce n’est pas déjà fait.
    
    touche. Donnez un nom à votre certificat, puis cliquez sur **Envoyer**.
    
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

Avant d’utiliser votre carte à puce pour la première fois, il est recommandé de cliquer sur **Supprimer mes informations de connexion** dans la page de connexion de Skype entreprise. Cela permet de supprimer les informations d’identification de connexion stockées sur votre ordinateur et d’éliminer une source possible d’erreur.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Pour vous connecter à Skype Entreprise avec vos informations d’identification de carte à puce

1. Démarrez le client Skype entreprise.
    
2. Dans l’écran Se connecter, tapez le nom de compte d’utilisateur de connexion dans la zone **Adresse de connexion**, puis cliquez sur **Se connecter**.
    
3. Si vous utilisez une carte à puce virtuelle, ignorez cette étape.
    
    Si vous utilisez une carte à puce physique, insérez la carte à puce dans le lecteur de cartes à puce, puis, lorsque vous y êtes invité, cliquez sur **OK** lorsque la carte est détectée.
    
4. Tapez le code confidentiel de votre carte à puce, puis cliquez sur **OK**.
    
    > [!NOTE]
    > Si le support technique ne vous a pas communiqué de code confidentiel, utilisez la valeur par défaut (12345678). 
  
## <a name="see-also"></a>Voir aussi

[Gestion de l’authentification à deux facteurs dans Skype entreprise Server](two-factor-authentication.md)
  
[Configurer l’authentification à deux facteurs dans Skype entreprise Server](configure-two-factor.md)
