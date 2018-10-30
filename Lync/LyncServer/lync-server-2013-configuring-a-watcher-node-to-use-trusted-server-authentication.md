---
title: "Conf. d’un nœud observateur pour l’util. de l’auth. des serveurs approuvés"
TOCtitle: "Conf. d’un nœud observateur pour l’util. de l’auth. des serveurs approuvés"
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204852(v=OCS.15)
ms:contentKeyID: 49297030
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’un nœud observateur pour l’utilisation de l’authentification des serveurs approuvés

 

_**Dernière rubrique modifiée :** 2012-10-22_

Si votre ordinateur de nœud observateur se trouve dans le réseau de périmètre, l’utilisation de l’authentification de type Serveur sécurisé permet de réduire considérablement les tâches d’administration à la gestion d’un certificat unique à la place des nombreux mots de passe de comptes d’utilisateurs.

La première étape de configuration de l’authentification de type Serveur sécurisé consiste à créer un pool d’applications approuvées afin d’héberger l’ordinateur de nœud observateur. Une fois le pool d’applications approuvées créé, vous devez configurer les transactions synthétiques de ce nœud observateur afin qu’elles s’exécutent sous forme d’application approuvée.

> [!NOTE]  
> Une application approuvée est une application qui dispose d’un statut d’approbation lui permettant de s’exécuter dans Lync Server 2013, mais qui ne fait pas partie intégrante du produit. Le statut d’application approuvée signifie que l’application n’a pas à s’authentifier chaque fois qu’elle s’exécute.

Pour créer un pool d’applications approuvées, ouvrez Lync Server 2013 Management Shell et exécutez une commande similaire à ce qui suit :

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

> [!NOTE]  
> Pour plus d’informations sur les paramètres utilisés dans la commande précédente, tapez ce qui suit à l’invite de Lync Server Management Shell :<br />
Get-Help New-CsTrustedApplicationPool -Full | more

Après avoir créé le pool d’applications approuvées, configurez l’ordinateur de nœud observateur afin qu’il exécute les transactions synthétiques sous forme d’application approuvée. Pour ce faire, utilisez l’applet de commande **New-CsTrustedApplication** et une commande similaire à ce qui suit :

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

Quand l’exécution de la commande précédente est terminée et que l’application approuvée a été créée, exécutez Enable-CsTopology pour vous assurer que les modifications sont appliquées :

    Enable-CsTopology

Après l’exécution de l’applet de commande Enable-CsTopology, nous vous recommandons de redémarrer l’ordinateur.

Pour vous assurer que la nouvelle application approuvée a été créée, tapez ce qui suit à l’invite de Lync Server Management Shell :

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

## Configuration d’un certificat par défaut sur le nœud observateur

Chaque nœud observateur doit posséder un certificat par défaut affecté à l’aide de l’Assistant Déploiement de Lync Server.

**Pour affecter un certificat par défaut**

1.  Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Lync Server**, puis sur **Assistant Déploiement de Lync Server**.

2.  Dans l’Assistant Déploiement de Lync Server, cliquez sur **Installer ou mettre à jour le système Lync Server**, puis cliquez sur **Exécuter** sous le titre **Demander, installer ou assigner les certificats**.
    
    > [!NOTE]  
    > Si le bouton <strong>Exécuter</strong> est désactivé, vous devrez peut-être d’abord cliquer sur <strong>Exécuter</strong> sous <strong>Installer le magasin de configurations local</strong>.

3.  Effectuez l’une des actions suivantes :
    
      - Si vous avez déjà un certificat qui peut être utilisé comme certificat par défaut, cliquez sur **Par défaut** dans l’Assistant Certificat, puis cliquez sur **Attribuer**. Suivez les étapes de l’Assistant permettant d’affecter un certificat pour affecter ce certificat.
    
      - Si vous devez demander un certificat à utiliser comme certificat par défaut, cliquez sur **Demander**, puis suivez les étapes de l’Assistant Demande de certificat pour demander ce certificat. Si vous utilisez les valeurs par défaut pour le certificat de serveur web, vous obtenez un certificat que vous pouvez affecter en tant que certificat par défaut.

## Installation et configuration d’un nœud observateur

Après avoir redémarré l’ordinateur de nœud observateur et configuré un certificat, vous devez exécuter le fichier Watchernode.msi. (Vous devez exécuter Watchernode.msi sur un ordinateur où les fichiers de l’Agent Operations Manager et les composants de base Lync Server 2013 sont installés.)

**Pour installer et configurer un nœud observateur**

1.  Ouvrez Lync Server Management Shell en cliquant sur **Démarrer**, sur **Tous les programmes**, sur **Lync Server**, puis sur **Lync Server Management Shell**.

2.  Dans Lync Server Management Shell, tapez la commande suivante, puis appuyez sur Entrée (spécifiez le chemin d’accès réel de votre copie de Watchernode.msi) :
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    > [!NOTE]  
    > Vous pouvez également exécuter Watchernode.msi à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur <strong>Démarrer</strong>, cliquez avec le bouton droit sur <strong>Invite de commandes</strong>, puis cliquez sur <strong>Exécuter en tant qu’administrateur</strong>. Quand la fenêtre de commande s’ouvre, tapez la même commande que celle indiquée précédemment.

Notez que la paire nom/valeur de la commande précédente Authentication=TrustedServer respecte l’emploi des majuscules et minuscules. Vous devez la taper exactement telle qu’elle est indiquée. La commande suivante échoue, car elle ne respecte pas l’emploi des majuscules et minuscules :

C:\\Tools\\Watchernode.msi authentication=trustedserver

Vous pouvez utiliser le mode TrustedServer uniquement avec les ordinateurs situés dans le réseau de périmètre. Quand un nœud observateur est exécuté en mode TrustedServer, les administrateurs n’ont pas à gérer les mots de passe d’utilisateurs de test sur l’ordinateur.

