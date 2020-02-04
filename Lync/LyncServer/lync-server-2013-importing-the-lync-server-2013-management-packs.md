---
title: 'Lync Server 2013 : importation des packs de gestion Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cc97cad4069c286f66707c34a9a1af7e87e97da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>Importation des packs d’administration de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Vous pouvez développer les fonctionnalités de System Center Operations Manager en installant des packs d’administration (logiciels qui déterminent les éléments que System Center Operations Manager peut surveiller et la façon dont ces éléments doivent être surveillés et la façon dont les alertes doivent être déclenchées et relat. Lync Server 2013 inclut deux packs d’administration System Center Operations Manager qui fournissent les fonctionnalités suivantes :

  - Le Pack de gestion des utilisateurs et des composants (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) effectue le suivi des problèmes du serveur Lync enregistrés dans les journaux d’événements, inscrits par des compteurs de performance ou enregistrés dans les enregistrements des détails des appels ou sur la qualité de l’utilisation (QoE). bases de données. Pour les problèmes critiques, System Center Operations Manager peut être configuré pour notifier immédiatement les administrateurs par courrier électronique, message instantané ou messagerie de courte durée de réception de messages. SMS est la technologie utilisée pour envoyer des messages texte d’un appareil mobile à un autre.)
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur la configuration de la notification Operations Manager, voir la notification de configuration <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>dans la bibliothèque TechNet à l’adresse.

    
    </div>

  - Le pack d’administration du contrôle actif (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) vérifie de manière proactive les principaux composants du serveur Lync tels que la connexion au système, l’échange de messages instantanés ou l’appel d’appels vers un téléphone situé sur le public. réseau téléphonique (RTC). Ces tests sont effectués à l’aide des cmdlets de transaction synthétique de Lync Server. Par exemple, vous pouvez utiliser l’applet de **contrôle CsIM** pour simuler une conversation de messagerie instantanée entre deux utilisateurs de test. Si cette conversation de messagerie simulée échoue, une alerte est générée.

Vous devez importer les modules de gestion. Si vous n’importez pas les packs d’administration, vous ne pouvez pas utiliser Operations Manager pour surveiller les événements de Lync Server ou exécuter les transactions synthétiques de Lync Server.

Le module Gestion des utilisateurs et des composants est utilisé uniquement pour contrôler Lync Server 2013. Si vous êtes dans un scénario de coexistence sur lequel vous avez installé Lync Server 2013 et Lync Server 2010, vous devez continuer à utiliser les packs de gestion Lync Server 2010 pour vos ordinateurs Lync Server 2010.

<div>


> [!NOTE]  
> Les packs de gestion pour Lync Server 2010 incluent le pack d’administration de l’analyseur Lync Server 2010 et le pack d’administration de la gestion des conversations de groupe de Lync Server 2010.



</div>

Vous pouvez utiliser l’un des outils suivants pour importer les packs d’administration :

  - **System Center Operations Manager**   avec cette méthode, vous utilisez le gestionnaire des opérations pour ajouter la surveillance de Lync Server.

  - **Operations Manager Shell**   vous pouvez utiliser le shell Operations Manager pour importer directement ou résoudre les problèmes que vous rencontrez lorsque vous importez des modules de gestion à l’aide de la console System Center Operations Manager.

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importation des packs d’administration avec System Center Operations Manager

1.  Téléchargez les fichiers Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp et Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.

2.  Dans System Center Operations Manager, cliquez sur **administration**.

3.  Dans le volet **administration** , cliquez avec le bouton droit sur **modules de gestion**, puis cliquez sur Importer des modules de **gestion**.

4.  Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Ajouter**, puis sur **Ajouter à partir du disque**.

5.  Dans la boîte de dialogue **connexion au catalogue en ligne** , cliquez sur **Annuler** pour empêcher Operations Manager de se connecter en ligne pour voir s’il existe des dépendances pour les packs de gestion de Lync Server. Si vous utilisez System Center Operations Manager 2012, cliquez sur **non**.

6.  Dans la boîte de dialogue **Sélectionner les modules de gestion à importer** , recherchez et sélectionnez les fichiers **Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP** et **Microsoft.ls.2013.Monitoring.ComponentAndUser.MP** , puis cliquez sur **ouvrir**. Pour sélectionner plusieurs fichiers dans la boîte de dialogue, cliquez sur le premier fichier, maintenez la touche CTRL enfoncée, puis cliquez sur le second fichier.

7.  Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Installer**. Si vous obtenez un message d’erreur et que l’installation échoue, cela signifie que les fichiers des packs d’administration se trouvent dans un dossier protégé par le contrôle du compte d’utilisateur Windows. Si tel est le cas, copiez les fichiers dans un autre dossier, puis redémarrez le processus d’importation et d’installation.

8.  Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Fermer**. Notez que le processus d’importation et d’installation peut nécessiter quelques minutes.

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Importation de modules de gestion à l’aide du shell Operations Manager

En règle générale, il est plus facile d’importer les modules de gestion à l’aide de Operations Manager. Toutefois, si une erreur se produit et que l’importation échoue, la console ne fournit pas toujours des rapports d’erreurs appropriés. Par comparaison, Operations Manager Shell fournit des informations détaillées. Si vous utilisez Operations Manager et que vous rencontrez des problèmes lors de l’importation d’un pack d’administration, importez le Pack à l’aide du shell Operations Manager. Le shell Operations Manager fournit des informations supplémentaires qui peuvent vous aider à déterminer la raison pour laquelle l’importation a échoué.

Si vous utilisez System Center Operations Manager 2007 R2, procédez comme suit :

1.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **System Center Operations Manager 2007 R2**, puis sur **Operations Manager Shell**.

2.  Dans le shell Operations Manager, tapez la commande suivante à l’invite de commandes, en utilisant le chemin réel vers votre copie du fichier Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, puis appuyez sur entrée :
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  Après avoir importé le premier pack d’administration, répétez le processus à l’aide du chemin d’accès de votre copie du fichier Microsoft.LS.2013.Monitoring.ComponentAndUser.mp :
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Fermez le shell Operations Manager.

Si vous utilisez System Center Operations Manager 2012, procédez comme suit :

1.  Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft System Center 2012**, sur **Operations Manager**, puis sur **Interpréteur de commandes d’Operations Manager**.

2.  Dans le shell Operations Manager, tapez la commande suivante à l’invite de commandes, en utilisant le chemin réel vers votre copie du fichier Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, puis appuyez sur entrée :
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  Après avoir importé le premier pack d’administration, répétez le processus à l’aide du chemin d’accès de votre copie du fichier Microsoft.LS.2013.Monitoring.ComponentAndUser.mp :
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

