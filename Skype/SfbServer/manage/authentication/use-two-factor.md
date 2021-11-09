---
title: Utiliser l’authentification à deux facteurs Skype Entreprise client et Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Résumé : Utilisez l’authentification à deux facteurs Skype Entreprise Server et Skype Entreprise.'
ms.openlocfilehash: 50237639172a70fdf68e1cca122d74cbf785f68e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839936"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Utiliser l’authentification à deux facteurs Skype Entreprise client et Skype Entreprise Server
 
**Résumé :** Utilisez l’authentification à deux facteurs Skype Entreprise Server et Skype Entreprise.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Connectez-vous Skype Entreprise pour la première fois

Vos informations de Skype Entreprise sont généralement configurées automatiquement. Mais la première fois que vous utilisez Skype Entreprise, vous de devez démarrer manuellement le client.
  
### <a name="to-sign-in-for-the-first-time"></a>Pour se connecter pour la première fois

1. Connectez-vous au réseau de votre organisation.
    
2. Sélectionnez   >  **Démarrer tous les programmes**  >  **Skype Entreprise**.
    
    Vous devriez voir l’écran de la signature.
    
    - Si la zone d’adresse de la signature est déjà remplie, confirmez que l’adresse affichée est correcte.
    
    - Si ce n’est pas correct ou si la zone est vide, entrez votre adresse de signature (elle est généralement la même que votre adresse e-mail).
    
    - Si une zone de mot de passe vide s’affiche, ajoutez votre mot de passe.
    
3. Sélectionnez **Se connectez.**
    
## <a name="sign-out-of-skype-for-business"></a>Se Skype Entreprise

Lorsque vous avez terminé d’utiliser Skype Entreprise, vous pouvez fermer l’affichage, quitter votre session ou quitter le programme, le tout à partir du menu Fichier. Le tableau suivant explique les différences entre les options.
  
|**Option**|**Fonction**|**Comment l’effectuer**|
|:-----|:-----|:-----|
|Fermer  <br/> |Ferme votre affichage, mais permet à la session Skype Entreprise identifiée avec votre ID d’utilisateur de continuer à s’exécuter. Ainsi, vous pouvez continuer à recevoir des notifications et interagir avec d’autres personnes. <br/> <br/> Vous pouvez obtenir l’affichage à tout moment en cliquant sur l’icône Skype Entreprise dans la barre des tâches ou dans la zone de notification en bas de l’écran.  <br/> | Dans la Skype Entreprise principale, faites l’une des choses suivantes : <br/> 1. Sélectionnez le **bouton Options,** puis sélectionnez **Fermer**  >  **le fichier.**  <br/> 2. Cliquez sur **le bouton** Fermer (X) dans le coin supérieur droit de la fenêtre. <br/> |
|Se sortir  <br/> |Met fin à la session associée à votre ID d’utilisateur, mais Skype Entreprise continue de s’exécuter en arrière-plan. Lorsque vous vous connectez, la fenêtre de signature s’affiche.  <br/> **Conseil :** Sélectionnez **Supprimer mes informations de connectez-vous** lorsque vous vous dé connectez pour supprimer l’enregistrement de votre ID d’inscription et de votre mot de passe de l’ordinateur. Cela peut faciliter la résolution des problèmes de connect. Il peut également vous aider à vous assurer que vos informations de connexion sont plus sécurisées en rendant difficile pour les utilisateurs non autorisés de se connecter avec vos informations d’identification. <br/> |Dans la Skype Entreprise principale, sélectionnez le bouton **Options,** puis **sélectionnez** Se  >  **sortir du fichier.**  <br/> |
|Quitter  <br/> |Met fin à Skype Entreprise session et arrête Skype Entreprise sur votre ordinateur. Après avoir quitté, si vous souhaitez redémarrer, sélectionnez **Démarrer** tous  >  **les** programmes > Skype Entreprise. <br/> |Dans la Skype Entreprise principale, sélectionnez le bouton **Options,** puis sélectionnez **Quitter**  >  **le fichier.**  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Connectez-vous Skype Entreprise avec une carte à puce

Certaines organisations utilisent désormais un processus de authentification en plusieurs étapes, appelé authentification à deux facteurs, pour renforcer la sécurité de leurs utilisateurs. Si vous êtes censé utiliser cette option, vous aurez besoin d’une « carte à puce » pour vous Skype Entreprise. Les cartes à puce peuvent être physiques ou virtuelles :
  
- **Physique** À propos de la taille d’une carte de crédit. Vous l’insérez dans un lecteur de carte à puce lorsque vous vous connectez.
    
- **Virtual** Pas un objet physique, mais un identificateur électronique qui est écrit sur une puce spéciale sur votre ordinateur, qui, par essence, crée la carte à puce sur votre ordinateur. Disponible uniquement pour une utilisation avec Windows 8 qui contiennent la puce TPM (Trusted Platform Module).
    
### <a name="enroll-your-smart-card"></a>Inscrire votre carte à puce

Avant de vous inscrire avec une carte à puce, celle-ci doit être « inscrite », c’est-à-dire que vos informations d’identification utilisateur doivent être identifiées avec la carte. C’est le cas si la carte est physique ou virtuelle. Ce processus a peut-être déjà été effectué par Skype Entreprise Server administrateur. Consultez-les si vous ne savez pas si cela a été fait.
  
> [!NOTE]
> Étant donné que chaque carte à puce virtuelle est associée uniquement à l’appareil sur qui elle est installée, une carte distincte doit être inscrite pour chaque ordinateur Windows 8 que vous utilisez. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Pour inscrire manuellement votre carte à puce

1. Log on the computer you’ll be running Skype Entreprise on.
    
2. À l’aide d’Internet Explorer, accédez à la page d’inscription web de l’autorité de certification de votre organisation. 
    
    Si vous ne l’avez pas déjà, demandez à votre administrateur Skype Entreprise Server’adresse web de cette ressource. L’URL ressemblera à ceci : https://MyCA .[ yourcompanyname].com/certsrv.
    
    > [!NOTE]
    > Si vous utilisez Internet Explorer 10, vous devrez peut-être afficher ce site web en mode de compatibilité. 
  
3. Lorsque vous êtes invité à vous connecter à la page de certification, connectez-vous à l’aide de votre compte de domaine (plutôt qu’en tant qu’administrateur de votre ordinateur).
    
4. Sur la page d’accueil du site web, **sélectionnez Demander un certificat.**
    
5. Sélectionnez **Demande avancée.**
    
6. Sélectionnez **Créer et envoyer une demande à cette ca,** puis cliquez sur **Suivant**.
    
7. Vous verrez maintenant une page appelée Station d’inscription de carte à puce. Approuvez la demande d’installation du contrôle ActiveX, puis remplissez le formulaire Demande de certificat avancée comme suit :
    
    a. Sélectionnez **l’utilisateur de carte à puce** dans **la** liste liste de listes de listes listes des modèles de certificats.
    
    b. Sélectionnez **Créer un jeu de clés.**
    
    c. Recherchez les informations sur le fabricant sur l’étiquette de votre carte à puce et sélectionnez ce fabricant dans la liste de listes des **CSP.**
    
    d. Sélectionnez **CSP** comme format de demande, s’il n’est pas déjà sélectionné.
    
    e. Sélectionnez **sha1 dans** la liste liste de listes de l’algorithme de hachage, s’il n’est pas déjà sélectionné.
    
    f. Donnez à votre certificat un nom que vous reconnaîtrez, puis cliquez sur **Envoyer.**
    
8. Insérez maintenant votre carte à puce vide dans le lecteur de carte attaché à la station d’inscription, puis cliquez **sur S’inscrire.**
    
9. Lorsque vous y invitez, entrez votre code confidentiel, puis cliquez sur **OK.**
    
    > [!NOTE]
    > Si votre support technique ne vous a pas attribué de code confidentiel spécial à utiliser pour inscrire votre carte à puce, utilisez la valeur par défaut du code confidentiel de carte à puce, 12345678. 
  
10. Sélectionnez l’option pour forcer l’utilisateur (vous) à modifier le code confidentiel la première fois que la carte à puce est utilisée.
    
11. Insérez maintenant votre carte à puce vide dans le lecteur de carte attaché à la station d’inscription, puis cliquez **sur S’inscrire.**
    
12. Lorsque vous y invitez, entrez votre code confidentiel, puis cliquez sur **OK.**
    
    > [!NOTE]
    > Si votre support technique ne vous a pas attribué de code confidentiel spécial à utiliser pour inscrire votre carte à puce, utilisez la valeur par défaut du code confidentiel de carte à puce, 12345678. 
  
13. Sélectionnez l’option pour forcer l’utilisateur (vous) à modifier le code confidentiel la première fois que la carte à puce est utilisée.
    
14. Cliquez **sur OK** pour confirmer que le certificat affiché a vos informations dessus.
    
15. Une fois que vous voyez l’avis que le certificat a été émis, cliquez sur **Installer** ce certificat pour terminer le processus d’inscription.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Connectez-vous à Skype Entreprise avec vos informations d’identification de carte à puce

Avant d’utiliser votre carte à puce pour la première  fois, il est recommandé de cliquer sur Supprimer mes informations de Skype Entreprise la page de se connectez. Cela permet d’effacer les informations d’identification de connexion stockées sur votre ordinateur et d’éliminer une source d’erreur possible.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Pour vous Skype Entreprise avec vos informations d’identification de carte à puce

1. Démarrez le client Skype Entreprise client.
    
2. Dans l’écran De connectez-vous, tapez le nom de votre compte d’utilisateur de signature dans la zone d’adresse de la signature, puis cliquez sur **Se connectez.** 
    
3. Si vous utilisez une carte à puce virtuelle, ignorez cette étape.
    
    Si vous utilisez une carte à puce physique, insérez-la dans votre lecteur de carte à puce et invitez-la à le faire, puis cliquez sur **OK** lorsque la carte est détectée.
    
4. Tapez le code confidentiel de votre carte à puce, puis cliquez sur **OK.**
    
    > [!NOTE]
    > Si votre support ne vous a pas affecté de code confidentiel de carte à puce, utilisez la valeur par défaut, 12345678. 
  
## <a name="see-also"></a>Voir aussi

[Gérer l’authentification à deux facteurs dans Skype Entreprise Server](two-factor-authentication.md)
  
[Configurer l’authentification à deux facteurs dans Skype Entreprise Server](configure-two-factor.md)
