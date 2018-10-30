---
title: Configuration de Windows 8 pour les cartes à puce virtuelles
TOCTitle: Configuration de Windows 8 pour les cartes à puce virtuelles
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn308564(v=OCS.15)
ms:contentKeyID: 56269577
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de Windows 8 pour les cartes à puce virtuelles

 

_**Dernière rubrique modifiée :** 2016-12-08_

Le coût de l’implémentation est l’un des facteurs dont vous devez tenir compte dans le cadre du déploiement de l’authentification à deux facteurs et de la technologie de carte à puce. Windows 8 inclut plusieurs nouvelles fonctionnalités de sécurité, dont la prise en charge des cartes à puce virtuelles.

Pour les ordinateurs équipés d’une puce de module de plateforme sécurisée conforme à la spécification version 1.2, les organisations peuvent désormais tirer parti des avantages d’une ouverture de session par carte à puce sans autre investissement matériel supplémentaire. Pour plus d’informations, voir la rubrique Utilisation des cartes à puce virtuelles avec Windows 8 à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).

## Configurer Windows 8 pour les cartes à puce virtuelles

1.  Connectez-vous à l’ordinateur Windows 8 à l’aide des informations d’identification d’un utilisateur prenant en charge Lync.

2.  Dans l’écran d’accueil de Windows 8, déplacez votre curseur dans le coin droit inférieur de l’écran.

3.  Sélectionnez l’option **Rechercher**, puis recherchez **Invite de commandes**.

4.  Cliquez avec le bouton droit sur **Invite de commande**, puis sélectionnez **Exécuter en tant qu’administrateur**.

5.  Ouvrez la console de gestion du module de plateforme sécurisée en exécutant la commande suivante :
    
        Tpm.msc

6.  À partir de la console de gestion du module de plateforme sécurisée, vérifiez que la spécification du module de plateforme sécurisée correspond à la version 1.2 au minimum.
    
    > [!NOTE]  
    > Si un message indiquant qu’aucun module de plateforme sécurisée compatible n’a été trouvé, vérifiez que l’ordinateur dispose d’un module de plateforme sécurisée compatible et que celui-ci est activé dans le BIOS système.

7.  Fermez la console de gestion du module de plateforme sécurisée.

8.  Sur la ligne de commande, créez une carte à puce virtuelle à l’aide de la commande suivante :
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    > [!NOTE]  
    > Pour fournir une valeur de code confidentiel personnalisée lors de la création de la carte à puce virtuelle, utilisez plutôt l’invite /pin.

9.  Sur la ligne de commande, ouvrez la console de gestion de l’ordinateur en exécutant la commande suivante :
    
        CompMgmt.msc

10. Dans la console de gestion de l’ordinateur, sélectionnez **Gestion des périphériques**.

11. Développez **Lecteurs de cartes à puce**.

12. Vérifiez que le nouveau lecteur de cartes à puce virtuelles a été correctement créé.

