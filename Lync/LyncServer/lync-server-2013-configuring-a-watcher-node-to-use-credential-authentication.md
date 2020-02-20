---
title: 'Lync Server 2013 : configuration d’un nœud observateur pour utiliser l’authentification des informations d’identification'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 473aba5f76d2c48d51b80ec413e003b3fe241d0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>Configuration d’un nœud observateur pour utiliser l’authentification des informations d’identification dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Si votre ordinateur de nœud observateur se trouve en dehors du réseau de périmètre, vous devez suivre une procédure légèrement différente afin de configurer ce nœud observateur pour qu’il exécute les transactions synthétiques. Surtout, évitez de créer un pool d’applications approuvées et une application approuvée. En revanche, vous devez installer un certificat permettant au nœud observateur d’envoyer des alertes à un ordinateur à l’intérieur du réseau de périmètre. En d’autres termes, vous devez effectuer deux tâches distinctes :

  - Mettre à jour l’appartenance au groupe « RTC Local Read-only Administrators » de l’ordinateur

  - Installer les fichiers de configuration du nœud observateur

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>Mise à jour de l’appartenance au groupe « RTC Local Read-Only Administrators »

Si votre ordinateur de nœud observateur se trouve en dehors du réseau de périmètre, vous devez ajouter le compte Service réseau au groupe « RTC Local Read-only Administrators » sur l’ordinateur de nœud observateur. Pour cela, procédez comme suit sur le nœud observateur :

1.  Cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Ordinateur** et cliquez sur **Gérer**.

2.  Dans le Gestionnaire de serveur, développez **Configuration**, **Utilisateurs et groupes locaux**, puis cliquez sur **Groupes**.

3.  Dans le volet Groupes, double-cliquez sur **RTC Local Read-only Administrators**.

4.  Dans la boîte de dialogue **RTC Local Read-only Administrators - Propriétés**, cliquez sur **Ajouter**.

5.  Dans la boîte de dialogue **Sélectionner des utilisateurs, des ordinateurs, des comptes de service ou des groupes**, cliquez sur **Emplacements**.

6.  Dans la boîte de dialogue **Emplacements**, sélectionnez le nom de l’ordinateur de nœud observateur, puis cliquez sur **OK**.

7.  Dans la zone **Entrez les noms d’objets à sélectionner**, tapez **Service réseau**, puis cliquez sur **OK**.

8.  Dans la boîte de dialogue **RTC Local Read-only Administrators - Propriétés**, cliquez sur **OK**, puis fermez le **Gestionnaire de serveur**.

Redémarrez l’ordinateur de nœud observateur.

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>Installation des fichiers de configuration du nœud observateur

Une fois que l’ordinateur du nœud observateur a redémarré, l’étape suivante consiste à exécuter le fichier Watchernode. msi. Pour exécuter ce fichier, ouvrez Lync Server 2013 Management Shell en cliquant sur **Démarrer**, sur **tous les programmes**, sur **Lync Server 2013**, puis sur **Lync Server Management Shell**. Dans Lync Server Management Shell, tapez la commande suivante, puis appuyez sur entrée (Assurez-vous et spécifiez le chemin d’accès réel à votre copie de Watchernode. msi) :

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> Comme indiqué précédemment, vous pouvez également exécuter Watchernode.msi à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur <STRONG>Démarrer</STRONG>, cliquez avec le bouton droit sur <STRONG>Invite de commandes</STRONG>, puis cliquez sur <STRONG>Exécuter en tant qu’administrateur</STRONG>. Lorsque la fenêtre de commande s’ouvre, tapez la même commande que précédemment.



</div>

Le mode Négocier est utilisé à chaque fois que le nœud observateur ne peut pas être configuré en tant que pool d’application approuvées. Dans ce mode, les administrateurs devront gérer les mots de passe des utilisateurs de test sur le nœud observateur.

</div>

</div>

<span> </span>

</div>

</div>

</div>

