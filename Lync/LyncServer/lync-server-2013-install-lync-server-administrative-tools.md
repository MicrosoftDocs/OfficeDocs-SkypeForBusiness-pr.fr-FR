---
title: 'Lync Server 2013 : Installation des outils d’administration Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1115d5848806f95d35a158f36b7689967cec5d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>Installation des outils d’administration Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Cette rubrique explique comment installer les outils d’administration que vous devez utiliser pour déployer et gérer Lync Server 2013. Les outils d’administration sont installés par défaut sur chaque serveur exécutant Lync Server 2013. Par ailleurs, vous pouvez installer les outils d’administration sur d’autres ordinateurs, par exemple des consoles d’administration dédiées. Nous vous recommandons vivement d’installer les outils d’administration sur un ordinateur qui se trouve dans le même domaine ou la même forêt que le déploiement de Lync Server 2013 que vous créez, car cela vous permet de vous assurer que les étapes de préparation des services de domaine Active Directory est déjà activée. terminé, qui vous permet d’utiliser les outils d’administration de cet ordinateur plus tard pour publier votre topologie.

Assurez-vous d’avoir examiné les exigences relatives aux privilèges d’infrastructure, de système d’exploitation, de logiciels et d’administrateur avant d’installer ou d’utiliser les outils d’administration de Lync Server 2013. Pour plus d’informations sur la configuration requise en matière d’infrastructure, voir la [Configuration requise infrastructure des outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Pour plus d’informations sur le système d’exploitation et la configuration logicielle requise pour l’installation des outils d’administration de Lync Server 2013, voir [prise en charge des systèmes d’exploitation serveur et outils dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md), et La [prise en charge et les exigences serveur supplémentaires dans Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md). Pour plus d’informations sur les droits d’utilisateur et les autorisations nécessaires pour installer et utiliser les outils, voir [droits d’administrateur et autorisations nécessaires pour l’installation et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

<div>


> [!IMPORTANT]  
> Si votre organisation nécessite que vous localisiez Internet Information Services (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers du serveur Lync dans la boîte de dialogue d’installation. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, les autres fichiers Lync Server 2013 sont déployés également sur ce lecteur.



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>Pour installer les outils d’administration de Lync Server 2013

1.  Ouvrez une session en tant qu’administrateur local (configuration minimale) pour l’ordinateur sur lequel vous voulez installer les outils d’administration. Si vous êtes connecté en tant qu’utilisateur standard sur les systèmes d’exploitation Windows Vista ou Windows 7, et que le contrôle de compte d’utilisateur (UAC) est activé, vous serez invité à entrer le nom d’utilisateur et le mot de passe d’administrateur local.

2.  Recherchez le support d’installation sur votre ordinateur, puis double-cliquez \\sur\\Setup\\. exe. exe.

3.  Si vous êtes invité à installer Microsoft Visual C++ 2008 distribuable, cliquez sur **Oui**.

4.  Dans la page de l’emplacement de l' **installation de Microsoft Lync Server 2013** , cliquez sur **OK**. Changez de chemin d’accès à un autre emplacement ou lecteur si vous avez besoin d’installer les fichiers à un autre emplacement.
    
    <div>
    

    > [!IMPORTANT]  
    > Si votre organisation nécessite que vous localisiez Internet Information Services (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès d’installation pour les fichiers Lync Server 2013 dans la boîte de dialogue d’installation. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, les autres fichiers Lync Server 2013 seront également déployés sur ce lecteur.

    
    </div>

5.  Sur la page **contrat de licence utilisateur final** , passez en revue les termes du contrat de licence, cliquez sur **J’accepte**, puis cliquez sur **OK**. Cette étape est nécessaire pour pouvoir continuer.

6.  Dans la page **Microsoft Lync Server 2013-Assistant Déploiement** , cliquez sur **installer les outils d’administration**.

7.  Lorsque l’installation est terminée, cliquez sur **quitter**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Ouvrez les outils d’administration de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Outils d’administration de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

