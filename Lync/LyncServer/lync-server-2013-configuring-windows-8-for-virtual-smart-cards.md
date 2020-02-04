---
title: 'Lync Server 2013 : configuration de Windows 8 pour les cartes à puce virtuelles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6298f7aa6a500a71c0b3732dd2f3d180e7192d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Configuration de Windows 8 pour l’utilisation des cartes à puce virtuelles avec Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-03_

Le coût de mise en œuvre est l’un des facteurs à prendre en compte dans le cadre du déploiement de l’authentification à deux facteurs et de la technologie de carte à puce. Windows 8 fournit un certain nombre de nouvelles fonctionnalités de sécurité et l’une des nouvelles fonctionnalités les plus intéressantes est la prise en charge des cartes à puce virtuelles.

Pour les ordinateurs équipés d’une puce de module de plateforme sécurisée conforme à la spécification version 1.2, les organisations peuvent désormais tirer parti des avantages d’une ouverture de session par carte à puce sans investissement matériel supplémentaire. Pour plus d’informations, reportez-vous à la rubrique [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)utilisation de cartes à puce virtuelles avec Windows 8.

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Configuration de Windows 8 pour les cartes à puce virtuelles

1.  Connectez-vous à l’ordinateur Windows 8 en utilisant les informations d’identification d’un utilisateur compatible Lync.

2.  Dans l’écran d’accueil de Windows 8, déplacez votre curseur dans le coin droit inférieur de l’écran.

3.  Sélectionnez l’option **Rechercher**, puis recherchez **Command Prompt**.

4.  Cliquez avec le bouton droit sur **Invite de commandes**, puis sélectionnez **Exécuter en tant qu’administrateur**.

5.  Ouvrez la console de gestion du module de plateforme sécurisée en exécutant la commande suivante :
    
        Tpm.msc

6.  À partir de la console de gestion du module de plateforme sécurisée, vérifiez que la spécification du module de plateforme sécurisée correspond à la version 1.2 au minimum.
    
    <div>
    

    > [!NOTE]  
    > Si un message indiquant qu’aucun module de plateforme sécurisée compatible n’a été trouvé, vérifiez que l’ordinateur dispose d’un module de plateforme sécurisée compatible et que celui-ci est activé dans le BIOS système.

    
    </div>

7.  Fermez la console de gestion du module de plateforme sécurisée.

8.  Dans l’invite de commandes, créez une carte à puce virtuelle à l’aide de la commande suivante :
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > Pour indiquer une valeur de code confidentiel personnalisée lors de la création de la carte à puce virtuelle, utilisez plutôt l’invite /pin.

    
    </div>

9.  Dans l’invite de commandes, ouvrez la console de gestion de l’ordinateur en exécutant la commande suivante :
    
        CompMgmt.msc

10. Dans la console de gestion de l’ordinateur, sélectionnez **Gestion des périphériques**.

11. Développez **Lecteurs de cartes à puce**.

12. Vérifiez que le lecteur de cartes à puce virtuelles a bien été créé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

