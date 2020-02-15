---
title: 'Lync Server 2013 : installation des outils d’administration Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8a0772244cf2158251b6a75a5b85b1adad86429
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>Installer les outils d’administration Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Cette rubrique décrit la procédure d’installation des outils d’administration nécessaires au déploiement et à la gestion de Lync Server 2013. Les outils d’administration sont installés par défaut sur chaque serveur exécutant Lync Server 2013. Vous pouvez également les installer sur d’autres ordinateurs, notamment des consoles d’administration dédiées. Nous vous recommandons vivement d’installer les outils d’administration sur un ordinateur qui se trouve dans le même domaine ou la même forêt que le déploiement Lync Server 2013 que vous créez, car en procédant ainsi, vous vous assurez que les étapes de préparation des services de domaine Active Directory sont déjà complet, qui vous permet d’utiliser les outils d’administration sur cet ordinateur ultérieurement pour publier votre topologie.

Avant d’installer ou d’utiliser les outils d’administration Lync Server 2013, veillez à consulter les conditions requises en matière d’infrastructure, de système d’exploitation, de logiciel et d’administrateur. Pour plus d’informations sur les exigences d’infrastructure, voir [administrative Tools infrastructure Requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Pour plus d’informations sur le système d’exploitation et la configuration logicielle requise pour l’installation des outils d’administration Lync Server 2013, voir [serveur et outils pris en charge par le système d’exploitation dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), la [configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md), ainsi que la [prise en charge et les exigences des serveurs supplémentaires dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Pour plus d’informations sur les droits utilisateur et les autorisations nécessaires à l’installation et à l’utilisation des outils, reportez-vous à la rubrique [droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

<div>


> [!IMPORTANT]  
> Si votre organisation exige que les services IIS (Internet Information Services) et l’ensemble des services web soient placés sur un lecteur autre que le lecteur système, vous pouvez modifier l’emplacement d’installation des fichiers Lync Server dans la boîte de dialogue Installation. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, les autres fichiers Lync Server 2013 seront également déployés sur ce lecteur.



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>Pour installer les outils d’administration Lync Server 2013

1.  Connectez-vous en tant qu’administrateur local (minimum requis) à l’ordinateur sur lequel vous souhaitez installer les outils d’administration. Si vous êtes connecté en tant qu’utilisateur standard sur les systèmes d’exploitation Windows Vista ou Windows 7 et que le contrôle de compte d’utilisateur (UAC) est activé, vous devez entrer votre nom d’utilisateur et votre mot de passe en qualité d’administrateur local ou ceux d’un domaine équivalent.

2.  Recherchez le support d’installation sur votre ordinateur, puis double-cliquez \\sur\\Setup\\amd64 Setup. exe.

3.  Si le système vous invite à installer le package distribuable Microsoft Visual C++ 2008, cliquez sur **Oui**.

4.  Sur la page **emplacement d’installation de Microsoft Lync Server 2013** , cliquez sur **OK**. Remplacez ce chemin par le chemin d’accès à un autre emplacement ou lecteur si vous souhaitez que les fichiers soient installés à un autre endroit.
    
    <div>
    

    > [!IMPORTANT]  
    > Si votre organisation exige que vous localisiez Internet Information Services (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers Lync Server 2013 dans la boîte de dialogue Configuration. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, les autres fichiers Lync Server 2013 seront également déployés sur ce lecteur.

    
    </div>

5.  Dans la page **Contrat de Licence Utilisateur Final**, vérifiez les termes du contrat de licence, cliquez sur **J’accepte**, puis cliquez sur **OK**. Cette étape est obligatoire pour continuer.

6.  Sur la page **Microsoft Lync Server 2013 – Assistant Déploiement** , cliquez sur **installer les outils d’administration**.

7.  Lorsque l’installation est terminée cliquez sur **Quitter**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Ouvrir les outils d’administration de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Outils d’administration Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

