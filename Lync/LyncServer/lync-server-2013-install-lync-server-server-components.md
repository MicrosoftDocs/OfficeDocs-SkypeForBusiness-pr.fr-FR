---
title: 'Lync Server 2013 : Installation des composants serveur Lync Server'
TOCTitle: Installation des composants serveur Lync Server
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398239(v=OCS.15)
ms:contentKeyID: 49296387
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation des composants serveur pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-05-05_

Avant d’effectuer les étapes suivantes, veillez à vous connecter au serveur avec un compte utilisateur de domaine correspondant à un administrateur local et à un membre du groupe RTCUniversalReadOnlyAdmins dans Active Directory.

Le Assistant Déploiement de Lync Server permet d’installer les composants nécessaires pour chaque rôle serveur Lync et d’activer le serveur. Cet article décrit les différentes étapes du déploiement d’un serveur Standard Edition ou d’un serveur frontal dans votre infrastructure Lync.

## Pour installer les composants Lync Server

1.  Si le Assistant Déploiement de Lync Server n’est pas en cours d’exécution, lancez-le sur le serveur où installer Lync.

2.  Cliquez sur **Installer ou mettre à jour le système Lync Server**.

3.  Dans l’Assistant Déploiement, confirmez que l’**Étape 1 : installer le magasin de configuration local** contient une coche verte. Cela implique que le serveur a réussi à installer une copie locale du magasin. Si elle n’est pas cochée, vous devez installer le magasin de configuration locale sur le serveur. Suivez la procédure décrite dans [Installation du magasin de configurations local dans Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md), puis revenez à cet écran.

4.  Lorsque vous êtes prêt à installer les composants Lync Server 2013 sur le serveur, cliquez sur **Exécuter** en regard de **Étape 2 : Installer ou supprimer des composants Lync Server**.

5.  Dans la page **Installer les composants Lync Server**, cliquez sur **Suivant** pour installer les composants, comme l’indique la topologie publiée.

6.  La page **Exécution des commandes** affiche un résumé des commandes et les informations relatives à la progression de l’installation. Une fois l’opération terminée, vous pouvez sélectionner un journal à afficher dans la liste, puis cliquer sur **Afficher le journal**.

7.  Lorsque l’installation des composants Lync Server 2013 est terminée et que vous avez consulté les journaux autant que nécessaire, cliquez sur **Terminer** pour finaliser cette étape.
    
    > [!NOTE]  
    > Si vous êtes invité à redémarrer le serveur (ce qu’il peut se passer si vous devez installer l’expérience Bureau Windows), effectuez réellement cette opération. Lorsque l’ordinateur est en état de fonctionner, vous devez répéter cette procédure à partir de l’étape 3 précédente (en résumé, exécutez une nouvelle fois l’Étape 2 de l’Assistant Déploiement).
