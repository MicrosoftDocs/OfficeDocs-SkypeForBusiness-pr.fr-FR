---
title: 'Lync Server 2013 : importation des packs d’administration Lync Server 2013'
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
ms.openlocfilehash: 3bd5f09d80aa86c9c0f692fbe0e744a445067e74
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>Importation des packs d’administration Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Vous pouvez étendre les fonctionnalités de System Center Operations Manager en installant les packs d’administration (logiciels qui déterminent les éléments que System Center Operations Manager peut surveiller, ainsi que la façon dont ces éléments doivent être surveillés et comment les alertes doivent être déclenchées et pourboire. Lync Server 2013 comprend deux packs d’administration System Center Operations Manager qui offrent les fonctionnalités suivantes :

  - Le pack d’administration des composants et des utilisateurs (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) effectue le suivi des problèmes Lync Server enregistrés dans les journaux des événements, enregistrés par des compteurs de performance ou consignés dans les enregistrements des détails des appels ou sur la qualité de l’expérience (QoE). bases. Pour les problèmes critiques, System Center Operations Manager peut être configuré pour informer immédiatement les administrateurs via la messagerie électronique, la messagerie instantanée ou la messagerie SMS (Short Message Service). SMS est la technologie utilisée pour envoyer des messages texte entre appareils mobiles.
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur la configuration de la notification Operations Manager, voir la page relative à <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>la configuration de la notification dans la bibliothèque TechNet à l’adresse.

    
    </div>

  - Le pack d’administration active Monitoring (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) teste de façon proactive les principaux composants de Lync Server, tels que la connexion au système, l’échange de messages instantanés ou l’appel à un téléphone situé sur le switch public. réseau téléphonique (PSTN). Ces tests sont effectués à l’aide des applets de commande de transaction synthétique Lync Server. Par exemple, vous pouvez utiliser l’applet de commande **Test-CsIM** pour simuler une conversation par message instantané entre deux utilisateurs test. Si cette conversation simulée échoue, une alerte est générée.

Vous devez importer les packs d’administration. Si vous n’importez pas les packs d’administration, vous ne pouvez pas utiliser Operations Manager pour surveiller les événements Lync Server ou exécuter des transactions synthétiques Lync Server.

Le pack d’administration des composants et des utilisateurs est utilisé uniquement pour analyser Lync Server 2013. Si vous êtes dans un scénario de coexistence dans lequel Lync Server 2013 et Lync Server 2010 sont installés, vous devez continuer à utiliser les packs d’administration Lync Server 2010 pour vos ordinateurs Lync Server 2010.

<div>


> [!NOTE]  
> Les packs d’administration de Lync Server 2010 incluent le pack d’administration de surveillance Lync Server 2010 et le pack d’administration d’analyse de la conversation de groupe Lync Server 2010.



</div>

Vous pouvez utiliser l’un des outils suivants pour importer les packs d’administration :

  - **System Center Operations Manager**   avec cette méthode, vous utilisez Operations Manager pour ajouter la surveillance de Lync Server.

  - **Microsoft Operations Manager Shell**   vous pouvez utiliser l’environnement de Shell Operations Manager pour importer directement ou pour résoudre les problèmes que vous rencontrez lorsque vous importez des packs d’administration à l’aide de la console System Center Operations Manager.

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importation des packs d’administration à l’aide de System Center Operations Manager

1.  Téléchargez les fichiers Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp et Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.

2.  Dans System Center Operations Manager, cliquez sur **administration**.

3.  Dans le volet **Administration**, cliquez avec le bouton droit sur **Packs d’administration**, puis cliquez sur **Importer les packs d’administration**.

4.  Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Ajouter**, puis sur **Ajouter à partir du disque**.

5.  Dans la boîte de dialogue **connexion au catalogue en ligne** , cliquez sur **Annuler** pour empêcher le gestionnaire des opérations de passer en mode connexion afin de déterminer s’il existe des dépendances pour les packs de gestion Lync Server. Si vous utilisez System Center Operations Manager 2012, cliquez sur **non**.

6.  Dans la boîte de dialogue **Sélectionner les packs d’administration à importer**, recherchez et sélectionnez les fichiers **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** et **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**, puis cliquez sur **Ouvrir**. Pour sélectionner plusieurs fichiers dans la boîte de dialogue, cliquez sur le premier fichier, maintenez la touche Ctrl enfoncée et cliquez sur un autre fichier.

7.  Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Installer**. Si vous obtenez un message d’erreur et que l’installation échoue, cela signifie que les fichiers des packs d’administration se trouvent dans un dossier protégé par le contrôle du compte d’utilisateur Windows. Si cela se produit, copiez les fichiers dans un autre dossier et redémarrez le processus d’importation et d’installation.

8.  Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Fermer**. Notez que le processus d’importation et d’installation peut prendre plusieurs minutes.

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Importation des packs d’administration à l’aide de l’environnement de commande Operations Manager

En règle générale, il est plus facile d’importer les packs d’administration à l’aide du gestionnaire des opérations. Toutefois, si une erreur se produit et que l’importation échoue, la console ne fournit pas toujours des rapports d’erreur appropriés. Par comparaison, le shell Operations Manager fournit des informations détaillées. Si vous utilisez Operations Manager et que vous rencontrez des problèmes lors de l’importation d’un pack d’administration, importez le Pack à l’aide de l’environnement de commande Operations Manager. Operations Manager Shell fournit des informations supplémentaires qui peuvent vous aider à déterminer la cause de l’échec de l’importation.

Si vous utilisez System Center Operations Manager 2007 R2, procédez comme suit :

1.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **System Center Operations Manager 2007 R2**, puis sur **environnement gestionnaire des opérations**.

2.  Dans l’environnement de ligne de commande Operations Manager, tapez la commande suivante à l’invite de commandes, en utilisant le chemin d’accès réel à votre copie du fichier Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, puis appuyez sur entrée :
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  Une fois le premier pack d’administration importé, répétez la procédure à l’aide du chemin vers votre copie du fichier Microsoft.LS.2013.Monitoring.ComponentAndUser.mp :
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Fermez le shell d’Operations Manager.

Si vous utilisez System Center Operations Manager 2012, effectuez la procédure suivante à la place :

1.  Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft System Center 2012**, sur **Operations Manager**, puis sur **environnement gestionnaire des opérations**.

2.  Dans l’environnement de ligne de commande Operations Manager, tapez la commande suivante à l’invite de commandes, en utilisant le chemin d’accès réel à votre copie du fichier Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, puis appuyez sur entrée :
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  Une fois le premier pack d’administration importé, répétez la procédure à l’aide du chemin vers votre copie du fichier Microsoft.LS.2013.Monitoring.ComponentAndUser.mp :
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

