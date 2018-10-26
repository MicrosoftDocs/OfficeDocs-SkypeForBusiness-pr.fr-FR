---
title: "LS 2013 : Serv. réact. ap. ferm. ports par Ass. Conf. de sécu. dans serv. int."
TOCTitle: Réactivation du serveur après la fermeture des ports par l’Assistant Configuration de la sécurité dans les services Internet (IIS)
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398851(v=OCS.15)
ms:contentKeyID: 49298876
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Réactivation du serveur après la fermeture des ports par l’Assistant Configuration de la sécurité dans les services Internet (IIS)

 

_**Dernière rubrique modifiée :** 2012-10-01_

Certains rôles Lync Server 2013 exécutent les services web sur le port 4443 des services Internet (IIS). L’exécution de l’Assistant Déploiement de Lync Server, Bootstrapper.exe, ou l’utilisation de l’applet de commande **Enable-CsComputer**, crée une exception dans le pare-feu et ouvre le port. Si vous exécutez l’Assistant Configuration de la sécurité de Windows Server 2008 R2 (ou d’autres scripts renforcés), le port 4443 sera bloqué, et les clients externes ne pourront pas contacter les services web. Pour rouvrir le port, vous pouvez soit modifier directement l’exception du pare-feu, soit réactiver le serveur.

## Pour réactiver le serveur à l’aide de l’Assistant Déploiement

1.  Dans la page Assistant Déploiement de Lync Server, cliquez sur **Exécuter** en regard de **Étape 2 : Installer ou supprimer des composants Lync Server** .

2.  Dans la page **Installer les composants Lync Server** , cliquez sur **Suivant** .

3.  Dans la page **Exécution de commandes** , lorsque l’état indique que la tâche est terminée, cliquez sur **Terminer** .
    
    > [!NOTE]  
    > Vous pouvez également utiliser bootstrapper.exe ou <strong>Enable-CsComputer</strong> pour réactiver le serveur.
