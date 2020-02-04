---
title: 'Lync Server 2013 : configuration d’un nœud FileSystemWatcher pour utiliser l’authentification des informations d’identification'
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
ms.openlocfilehash: 0d0fa67c4ef2688035471d2290ead78123f73239
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>Configuration d’un nœud FileSystemWatcher pour utiliser l’authentification des informations d’identification dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Si votre ordinateur de nœud de l’observateur se trouve en dehors du réseau de périmètre, vous devez suivre une procédure légèrement différente pour configurer le nœud de l’observateur pour qu’il exécute des transactions synthétiques. Plus précisément, il est préférable de ne pas créer de pool d’applications fiable et d’application fiable, et vous devez installer un certificat qui permet au nœud d’observation d’envoyer des alertes à un ordinateur à l’intérieur du réseau de périmètre. Cela signifie que vous devez effectuer deux tâches distinctes :

  - Mettre à jour l’appartenance au groupe d’administrateurs en lecture seule local de l’ordinateur

  - Installer les fichiers de configuration de nœud d’observation

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>Mise à jour de l’appartenance au groupe d’administrateurs en lecture seule locale RTC

Si votre nœud FileSystemWatcher se trouve en dehors du réseau de périmètre, vous devez ajouter le compte de service réseau au groupe d’administrateurs en lecture seule locale RTC sur l’ordinateur de nœud d’observation. Pour cela, suivez la procédure ci-dessous sur le nœud d’observation :

1.  Cliquez sur **Démarrer**, cliquez avec le bouton droit sur **ordinateur**, puis cliquez sur **gérer**.

2.  Dans le gestionnaire de serveur, développez **configuration**, **utilisateurs et groupes locaux**, puis cliquez sur **groupes**.

3.  Dans le volet groupes, cliquez deux fois sur **RTC local en lecture seule**.

4.  Dans la boîte de dialogue Propriétés de l' **administrateur en lecture seule** , cliquez sur **Ajouter**.

5.  Dans la boîte de dialogue **Sélectionner des utilisateurs, des ordinateurs, des comptes de service ou des groupes** , cliquez sur **emplacements**.

6.  Dans la boîte de dialogue **emplacements** , sélectionnez le nom de l’ordinateur du nœud d’observation, puis cliquez sur **OK**.

7.  Dans la zone **Entrez les noms des objets à sélectionner** , tapez **service réseau**, puis cliquez sur **OK**.

8.  Dans la boîte de dialogue Propriétés de l' **administrateur en lecture seule locale RTC** , cliquez sur **OK**, puis fermez le **Gestionnaire de serveur**.

Redémarrez l’ordinateur de nœud observateur.

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>Installation des fichiers de configuration de nœud d’observation

Après le redémarrage de l’ordinateur de nœud d’observateur, l’étape suivante consiste à exécuter le fichier Watchernode. msi. Pour exécuter ce fichier, ouvrez Lync Server 2013 Management Shell en cliquant sur **Démarrer**, puis sur **tous les programmes**, sur **Lync Server 2013**et sur **Lync Server Management Shell**. Dans Lync Server Management Shell, tapez la commande suivante, puis appuyez sur entrée (Vérifiez et spécifiez le chemin d’accès réel à votre copie de Watchernode. msi) :

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> Comme indiqué précédemment, Watchernode. msi peut également être exécuté à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur <STRONG>Démarrer</STRONG>, cliquez avec le bouton droit sur <STRONG>Invite de commandes</STRONG>, puis cliquez sur <STRONG>Exécuter en tant qu’administrateur</STRONG>. Lorsque la fenêtre de commande s’ouvre, tapez la même commande que celle présentée précédemment.



</div>

Le mode Négocier est utilisé chaque fois que le nœud observateur ne peut pas être configuré comme pool d’application approuvées. Dans ce mode, les administrateurs devront gérer les mots de passe des utilisateurs de test sur le nœud observateur.

</div>

</div>

<span> </span>

</div>

</div>

</div>

