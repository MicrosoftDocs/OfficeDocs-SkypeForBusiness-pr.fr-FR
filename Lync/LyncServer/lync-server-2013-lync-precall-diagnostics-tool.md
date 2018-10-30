---
title: Outil de diagnostic avant appel de Lync dans Lync Server 2013
TOCTitle: Outil de diagnostic avant appel de Lync dans Lync Server 2013
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn451255(v=OCS.15)
ms:contentKeyID: 59602867
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Outil de diagnostic avant appel de Lync dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

L’outil de diagnostic avant appel de Lync (PreCall Diagnostics, PCD) est une application cliente qui vous permet de savoir quelle incidence l’état actuel du réseau peut avoir sur la qualité audio d’un appel Voix Entreprise à venir.

L’outil PCD est particulièrement utile dans des situations où le dernier tronçon d’un réseau est probablement le plus faible (par exemple, des ordinateurs portables sur un réseau Wi-Fi public ou des utilisateurs à domicile). Il crée un petit flux de paquets qui traverse ce dernier segment du réseau. Il analyse ensuite le flux de paquets afin de mesurer comment la gigue et la perte de paquets sur ce segment peuvent nuire à la qualité, puis il génère un rapport à cet effet. Vous pouvez exécuter l’outil PCD en continu sur le client, même lorsque vous effectuez des appels. Le flux de paquets n’a pas une incidence considérable sur la bande passante.

**La dernière version de l’outil PCD, version 1.1, inclut les améliorations suivantes :**

  - Prise en charge de mots de passe plus longs, qui peuvent désormais contenir jusqu’à 127 caractères

  - Diagnostics supplémentaires pour les problèmes d’authentification

  - Meilleure prise en charge des déploiements hybrides Lync

  - Mises à jour de la sélection des informations d’identification

  - Améliorations de la stabilité

Vos commentaires sont les bienvenus. Envoyez vos questions de support technique ou problèmes à l’alias [PCD Feedback](mailto:pcdfb@microsoft.com) à l’adresse <pcdfb@microsoft.com>.

Cette rubrique inclut les sections suivantes :

  - Versions de l’outil PCD de Lync

  - Configuration requise pour l’outil PCD de Lync

  - Fonctionnalités de l'outil PCD de Lync

  - Exécution de l'outil PCD de Lync

  - Désinstallation de l'outil PCD de Lync

## Versions de l’outil PCD de Lync

Cette rubrique décrit les versions suivantes de l’outil (téléchargeables gratuitement) :

  - Application de bureau Windows ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))

  - Application Windows 8 Modern ([http://go.microsoft.com/fwlink/?LinkId=322110](http://go.microsoft.com/fwlink/p/?linkid=322110))

> [!NOTE]  
> Les utilisateurs d’Office 365 Lync peuvent utiliser les deux versions de l’outil PCD.

Si vous voulez utiliser une version précédente de l’outil PCD, consultez ce qui suit :

  - La version 32 bits de l’outil PCD peut être téléchargée gratuitement à partir du Centre de téléchargement Microsoft via la page [Office Communications Server 2007 R2, PreCallDiagnostic Resource Kit Tool (32 Bit) (Outil du Kit de ressources PreCallDiagnostic d’Office Communications Server 2007 R2 (32 bits))](http://go.microsoft.com/fwlink/p/?linkid=164769).

  - La version 64 bits est incluse dans les outils du Kit de ressources de Microsoft Office Communications Server 2007 R2, lui-même disponible sur le site du Centre de téléchargement Microsoft via la page [Office Communications Server 2007 R2 Resource Kit Tools (Outils du Kit de ressources d’Office Communications Server 2007 R2)](http://go.microsoft.com/fwlink/p/?linkid=145159).

## Configuration requise pour l’outil PCD de Lync

> [!NOTE]  
> L’outil PCD requiert l’installation et la configuration de l’API web Communications unifiées (UCWA) pour la prise en charge des clients mobiles dans le déploiement Lync Server. UCWA est installée avec Lync Server.

## Configuration requise de l’application de bureau Windows

  - Une édition quelconque du système d’exploitation Windows 7 ou Windows 8

  - Microsoft .NET Framework 4.5 (accessible à l’adresse [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790))

## Configuration requise de l’application Windows 8 Modern

  - Une édition quelconque du système d’exploitation Windows 8

  - Microsoft .NET Framework 4.5 (accessible à l’adresse [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790))

## Fonctionnalités de l’outil PCD de Lync

L’outil PCD de Lync inclut les fonctionnalités suivantes :

  - Exécution à la demande par défaut (rafales de 2 minutes)

  - Exécution en mode Toujours activé (jusqu’à 24 heures dans l’affichage aligné)

  - Affichage historique de vos exécutions de test

  - Diagnostic des échecs de connexion (outil PCD de Lync pour Windows 8 uniquement)

![Capture d’écran de la connexion en cours aux fonctionnalités Lync PCD](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Capture d’écran de la connexion en cours aux fonctionnalités Lync PCD")

  - Affichage graphique des mesures du réseau (note MOS qualité réseau, perte de paquets et gigue du délai d’arrivée dans l’affichage plein écran et l’affichage aligné)

**Affichage plein écran**

![Graphiques des résultats de test de l’outil PreCall Diagnostic](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Graphiques des résultats de test de l’outil PreCall Diagnostic")

**Affichage aligné**

![Résultats des tests d’utilisation de l’outil PreCall Diagnostic](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Résultats des tests d’utilisation de l’outil PreCall Diagnostic")

## Exécution de l’outil PCD de Lync

## Exécution de l’application de bureau Windows

1.  Pour démarrer l’outil PCD sur un système Windows 7, sélectionnez **PreCall Diagnostics** dans le menu **Démarrer**.
    
    Pour démarrer l’outil PCD sur un système Windows 8, sélectionnez l’icône sur votre écran Démarrer ou recherchez « PreCall Diagnostics ».
    
    ![Icône de l’outil PreCall Diagnostic](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icône de l’outil PreCall Diagnostic")

2.  Au démarrage de l’outil, sélectionnez votre méthode préférée pour la fourniture des informations d’identification, le mode de fonctionnement du réseau dans la boîte de dialogue **PreCall Diagnostics Tool Options (Options de l’outil de diagnostic avant appel)**, puis cliquez sur **OK** :

3.  Cliquez sur le bouton **Start Test (Démarrer le test)** pour lancer l’exécution des diagnostics.
    
    Si vous avez sélectionné l’option **Use network credentials (Utiliser les informations d’identification réseau)**, le test commence immédiatement.
    
    Si vous avez sélectionné l’option **Let me enter my credentials (Me permettre d’entrer mes informations d’identification)**, la boîte de dialogue **Windows Security (Sécurité de Windows)** s’ouvre. Une fois que vous avez entré vos informations d’identification, le test commence.

## Exécution de l’application Windows 8 Modern


1.  Pour démarrer l’outil PCD, sélectionnez l’icône sur votre écran Démarrer ou recherchez « PreCall Diagnostics ».
    
    ![Icône de l’outil PreCall Diagnostic](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icône de l’outil PreCall Diagnostic")

2.  Au démarrage de l’outil, indiquez vos informations d’identification Lync, puis cliquez sur **OK**.
    
    ![Connexion à l’outil de diagnostic avant appel de Lync](images/Dn451255.88039914-4c68-48f6-a9fa-58cb4e3f3488(OCS.15).jpg "Connexion à l’outil de diagnostic avant appel de Lync")

3.  Cliquez sur le bouton **Start test (Démarrer le test)** pour lancer l’exécution des diagnostics.

## Désinstallation de l’outil PCD de Lync

Pour supprimer l’outil PCD de Lync, suivez la procédure adaptée à votre système d’exploitation :

  - Sur un système Windows 7, ouvrez le **Panneau de configuration**, sélectionnez **Programmes et fonctionnalités**, puis double-cliquez sur **Lync 2013 PreCall Diagnostics**.

  - Sur un système Windows 8, cliquez avec le bouton droit sur la vignette PCD, puis cliquez sur **Désinstaller** dans la barre d’application en bas de l’écran de démarrage.

