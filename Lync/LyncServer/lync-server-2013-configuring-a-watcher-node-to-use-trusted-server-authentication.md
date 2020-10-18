---
title: Configuration d’un nœud observateur pour utiliser l’authentification de serveur approuvé
description: Configuration d’un nœud observateur pour utiliser l’authentification de serveur approuvé.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 247d628f936808a01780c7adc497342baedbbecb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576310"
---
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>Configuration d’un nœud observateur dans Lync Server 2013 pour utiliser l’authentification de serveur approuvé

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Si votre ordinateur de nœud observateur se trouve dans le réseau de périmètre, l’utilisation de l’authentification de type Serveur sécurisé permet de réduire considérablement les tâches d’administration à la gestion d’un certificat unique à la place des nombreux mots de passe de comptes d’utilisateurs.

La première étape de configuration de l’authentification de type Serveur sécurisé consiste à créer un pool d’applications approuvées afin d’héberger l’ordinateur de nœud observateur. Une fois le pool d’applications approuvées créé, vous devez configurer les transactions synthétiques de ce nœud observateur afin qu’elles s’exécutent sous forme d’application approuvée.

<div>


> [!NOTE]
> Une application approuvée est une application à laquelle est attribuée un État approuvé à exécuter dans le cadre de Lync Server 2013, mais ce n’est pas une partie intégrée du produit. Le statut d’application approuvée signifie que l’application n’a pas à s’authentifier chaque fois qu’elle s’exécute.



</div>

Pour créer un pool d’applications approuvées, ouvrez Lync Server 2013 Management Shell et exécutez une commande semblable à celle-ci :

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> Pour plus d’informations sur les paramètres utilisés dans la commande précédente, tapez ce qui suit à l’invite de Lync Server Management Shell :<BR>Get-Help New-CsTrustedApplicationPool -Full | more



</div>

Après avoir créé le pool d’applications approuvées, configurez l’ordinateur de nœud observateur afin qu’il exécute les transactions synthétiques sous forme d’application approuvée. Pour ce faire, utilisez l’applet de commande **New-CsTrustedApplication** et une commande similaire à ce qui suit :

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

Quand l’exécution de la commande précédente est terminée et que l’application approuvée a été créée, exécutez Enable-CsTopology pour vous assurer que les modifications sont appliquées :

    Enable-CsTopology

Après l’exécution de l’applet de commande Enable-CsTopology, nous vous recommandons de redémarrer l’ordinateur.

Pour vérifier que la nouvelle application approuvée a été créée, tapez ce qui suit à l’invite Lync Server Management Shell :

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>Configuration d’un certificat par défaut sur le nœud observateur

Chaque nœud observateur doit avoir un certificat par défaut affecté à l’aide de l’Assistant Déploiement de Lync Server.

**Pour affecter un certificat par défaut**

1.  Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Lync Server**, puis sur **Assistant Déploiement Lync Server**.

2.  Dans l’Assistant Déploiement Lync Server, cliquez sur **installer ou mettre à jour le système Lync Server** , puis cliquez sur **exécuter** sous le titre **requête, installer ou assigner un certificat**.
    
    <div>
    

    > [!NOTE]
    > Si le bouton <STRONG>Exécuter</STRONG> est désactivé, vous devrez peut-être d’abord cliquer sur <STRONG>Exécuter</STRONG> sous <STRONG>Installer le magasin de configurations local</STRONG>.

    
    </div>

3.  Effectuez l’une des actions suivantes :
    
      - Si vous avez déjà un certificat qui peut être utilisé comme certificat par défaut, cliquez sur **Par défaut** dans l’Assistant Certificat, puis cliquez sur **Attribuer**. Suivez les étapes de l’Assistant permettant d’affecter un certificat pour affecter ce certificat.
    
      - Si vous devez demander un certificat à utiliser comme certificat par défaut, cliquez sur **Demander**, puis suivez les étapes de l’Assistant Demande de certificat pour demander ce certificat. Si vous utilisez les valeurs par défaut pour le certificat de serveur web, vous obtenez un certificat que vous pouvez affecter en tant que certificat par défaut.

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>Installation et configuration d’un nœud observateur

Après avoir redémarré l’ordinateur de nœud observateur et configuré un certificat, vous devez exécuter le fichier Watchernode.msi. (Vous devez exécuter Watchernode.msi sur un ordinateur où sont installés les fichiers de l’agent Operations Manager et les composants principaux de Lync Server 2013.)

**Pour installer et configurer un nœud observateur**

1.  Ouvrez Lync Server Management Shell en cliquant sur **Démarrer**, sur **tous les programmes**, sur **Lync Server**, puis sur **Lync Server Management Shell**.

2.  Dans Lync Server Management Shell, tapez la commande suivante, puis appuyez sur entrée (spécifiez le chemin d’accès réel à votre copie de Watchernode.msi) :
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > Vous pouvez également exécuter Watchernode.msi à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur <STRONG>Démarrer</STRONG>, cliquez avec le bouton droit sur <STRONG>Invite de commandes</STRONG>, puis cliquez sur <STRONG>Exécuter en tant qu’administrateur</STRONG>. Quand la fenêtre de commande s’ouvre, tapez la même commande que celle indiquée précédemment.

    
    </div>

Notez que la paire nom/valeur de la commande précédente Authentication=TrustedServer respecte l’emploi des majuscules et minuscules. Vous devez la taper exactement telle qu’elle est indiquée. La commande suivante échoue, car elle ne respecte pas l’emploi des majuscules et minuscules :

C : \\ outils \\Watchernode.msi Authentication = Trustedserver

Vous pouvez utiliser le mode TrustedServer uniquement avec les ordinateurs situés dans le réseau de périmètre. Quand un nœud observateur est exécuté en mode TrustedServer, les administrateurs n’ont pas à gérer les mots de passe d’utilisateurs de test sur l’ordinateur.

</div>

</div>

<span> </span>

</div>

</div>

</div>

