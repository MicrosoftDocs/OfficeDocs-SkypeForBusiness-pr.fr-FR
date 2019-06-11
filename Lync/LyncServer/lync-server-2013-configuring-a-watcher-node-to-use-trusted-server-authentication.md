---
title: Configuration d’un nœud FileSystemWatcher pour utiliser l’authentification de serveur approuvé
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6634fa55424190d2e0a05aece38d88977d2f6bca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>Configuration d’un nœud FileSystemWatcher dans Lync Server 2013 de façon à utiliser l’authentification de serveur approuvé

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

Si votre ordinateur de nœud d’observateur se trouve à l’intérieur du réseau de périmètre, l’utilisation de l’authentification de serveur approuvé peut considérablement réduire les taxes d’administration pour gérer un seul certificat plutôt que de nombreux mots de passe de compte d’utilisateur.

La première étape de la configuration de l’authentification de serveur approuvé consiste à créer un pool d’applications approuvé pour héberger l’ordinateur de nœud d’observation. Une fois le pool d’applications approuvé créé, vous devez configurer les transactions synthétiques sur le nœud de l’observateur pour qu’il s’exécute en tant qu’application approuvée.

<div>


> [!NOTE]
> Une application fiable est une application dotée d’un État approuvé à exécuter dans le cadre de Lync Server 2013, mais qui n’est pas une partie intégrante du produit. Le statut approuvé signifie que l’application n’a pas à s’authentifier chaque fois qu’elle est exécutée.



</div>

Pour créer un pool d’applications approuvé, ouvrez Lync Server 2013 Management Shell et exécutez une commande semblable à ce qui suit:

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> Pour plus d’informations sur les paramètres utilisés dans la commande précédente, tapez ce qui suit à l’invite Lync Server Management Shell:<BR>Get-nouvelle-CsTrustedApplicationPool-complet | nombre



</div>

Après avoir créé le pool d’applications approuvé, configurez l’ordinateur de nœud d’observation pour qu’il exécute des transactions synthétiques en tant qu’application approuvée. Pour ce faire, vous pouvez utiliser l’applet **de commande New-CsTrustedApplication** et une commande similaire à celle-ci:

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

Une fois la commande précédente terminée et l’application de confiance créée, exécutez Enable-CsTopology pour vous assurer que les modifications entrent en vigueur:

    Enable-CsTopology

Après avoir exécuté enable-CsTopology, il est recommandé de redémarrer l’ordinateur.

Pour vérifier que la nouvelle application fiable a été créée, tapez les informations suivantes à l’invite Lync Server Management Shell:

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>Configuration d’un certificat par défaut sur le nœud d’observation

Un certificat par défaut doit être attribué à chaque nœud de l’observateur à l’aide de l’Assistant Déploiement de Lync Server.

**Pour attribuer un certificat par défaut**

1.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Lync Server**, puis sur **Assistant Déploiement de Lync Server**.

2.  Dans l’Assistant Déploiement de Lync Server, cliquez sur **installer ou mettre à jour le système de serveur Lync** , puis cliquez sur **exécuter** sous le titre **demande, installer ou attribuer un certificat**.
    
    <div>
    

    > [!NOTE]
    > Si le bouton <STRONG>exécuter</STRONG> est désactivé, vous devrez peut-être cliquer d’abord sur <STRONG>exécuter</STRONG> sous installer le <STRONG>magasin de configuration local</STRONG>.

    
    </div>

3.  Effectuez l’une des actions suivantes :
    
      - Si vous disposez déjà d’un certificat qui peut être utilisé comme certificat par défaut, cliquez sur **par défaut** dans l’Assistant certificat, puis cliquez sur **affecter**. Suivez les étapes de l’Assistant permettant d’affecter un certificat pour affecter ce certificat.
    
      - Si vous avez besoin de demander un certificat pour utiliser le certificat par défaut, cliquez sur **demander** , puis suivez les étapes de l’Assistant demande de certificat pour demander ce certificat. Si vous utilisez les valeurs par défaut pour le certificat de serveur web, vous obtenez un certificat que vous pouvez affecter comme certificat par défaut.

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>Installation et configuration d’un nœud FileSystemWatcher

Après avoir redémarré l’ordinateur du nœud d’observation et configuré un certificat, vous devez exécuter le fichier Watchernode. msi. (Vous devez exécuter Watchernode. msi sur un ordinateur sur lequel sont installés les fichiers agent Operations Manager et les composants principaux de Lync Server 2013.)

**Pour installer et configurer un nœud FileSystemWatcher**

1.  Ouvrez Lync Server Management Shell en cliquant sur **Démarrer**, puis sur **tous les programmes**, sur **Lync Server**et sur **Lync Server Management Shell**.

2.  Dans Lync Server Management Shell, tapez la commande suivante, puis appuyez sur entrée (spécifiez le chemin d’accès réel à votre copie de Watchernode. msi):
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > Vous pouvez également exécuter Watchernode. msi à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur <STRONG>Démarrer</STRONG>, cliquez avec le bouton droit sur <STRONG>Invite de commandes</STRONG>, puis cliquez sur <STRONG>Exécuter en tant qu’administrateur</STRONG>. Lorsque la fenêtre de commande s’ouvre, tapez la même commande précédente.

    
    </div>

Notez que la paire nom/valeur dans l’authentification de commande précédente = TrustedServer est sensible à la casse. Vous devez la taper exactement comme indiqué. La commande suivante échoue, car elle n’utilise pas la casse correcte pour les lettres:

C:\\outils\\Watchernode. msi d’authentification = Trustedserver

Vous pouvez utiliser le mode TrustedServer uniquement avec des ordinateurs situés dans le réseau de périmètre. Lorsqu’un nœud d’observateur est en cours d’exécution en mode TrustedServer, les administrateurs n’ont pas besoin de mettre à jour les mots de passe des utilisateurs de tests sur l’ordinateur.

</div>

</div>

<span> </span>

</div>

</div>

</div>

