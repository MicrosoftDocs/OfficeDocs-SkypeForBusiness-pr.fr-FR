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
ms.openlocfilehash: 29fa0be32f5a2c2a0af0b63dadddda3038675adf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Configuration de Windows 8 pour l’utilisation de cartes à puce virtuelles avec Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-03_

L’un des facteurs à prendre en compte lors du déploiement de l’authentification à deux facteurs et de la technologie de carte à puce est le coût de mise en œuvre. Windows 8 fournit un certain nombre de nouvelles fonctionnalités de sécurité et l’une des nouvelles fonctionnalités les plus intéressantes est la prise en charge des cartes à puce virtuelles.

Pour les ordinateurs équipés d’un processeur de module de plateforme sécurisée (TPM) qui correspond à la version de spécification 1,2, les organisations peuvent désormais bénéficier des avantages de l’ouverture de session par carte à puce sans faire d’autres investissements sur le matériel. Pour plus d’informations, consultez la rubrique utilisation de cartes à puce [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365)virtuelles avec Windows 8 à l’adresse.

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Pour configurer Windows 8 pour les cartes à puce virtuelles

1.  Connectez-vous à l’ordinateur Windows 8 à l’aide des informations d’identification d’un utilisateur à extension Lync.

2.  À l’écran d’accueil de Windows 8, déplacez votre curseur vers le coin inférieur droit de l’écran.

3.  Sélectionnez l’option **Rechercher** , puis recherchez invite de **commandes**.

4.  Cliquez avec le bouton droit sur **invite de commandes**, puis sélectionnez **exécuter en tant qu’administrateur**.

5.  Ouvrez la console de gestion du module de plateforme sécurisée (TPM) en exécutant la commande suivante :
    
        Tpm.msc

6.  À partir de la console de gestion du module de plateforme sécurisée, vérifiez que la version de votre spécification de TPM est d’au moins 1,2
    
    <div>
    

    > [!NOTE]  
    > Si vous recevez une boîte de dialogue indiquant qu’un module de plateforme de confiance compatible (TPM) est introuvable, vérifiez que l’ordinateur dispose d’un module TPM compatible et qu’il est activé dans le BIOS système.

    
    </div>

7.  Fermer la console de gestion du TPM

8.  À partir de l’invite de commandes, créez une carte à puce virtuelle à l’aide de la commande suivante :
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > Pour fournir une valeur de code confidentiel personnalisée lors de la création de la carte à puce virtuelle, utilisez à la place/pin prompt.

    
    </div>

9.  À partir de l’invite de commandes, ouvrez la console de gestion de l’ordinateur en exécutant la commande suivante :
    
        CompMgmt.msc

10. Dans la console de gestion de l’ordinateur, sélectionnez **gestion des appareils**.

11. Développez **lecteurs de cartes à puce**.

12. Vérifiez que le nouveau lecteur de carte à puce virtuelle a été créé avec succès.

</div>

</div>

<span> </span>

</div>

</div>

</div>

