---
title: 'Lync Server 2013 : activation des utilisateurs pour la messagerie vocale hébergée'
description: 'Lync Server 2013 : activation des utilisateurs pour la messagerie vocale hébergée.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3853a70d433c09029a02f2ca6256b5988defdcb2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572740"
---
# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Activer les utilisateurs pour la messagerie vocale hébergée dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-24_

Suivez la procédure pour activer les utilisateurs Lync Server 2013 pour la messagerie vocale sur un service de messagerie unifiée Exchange hébergé.

Pour plus d’informations, voir [Hosted Exchange User Management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) dans la documentation de planification.

Pour plus d’informations sur la cmdlet [Set-Csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , voir la documentation de Lync Server Management Shell.

<div>


> [!IMPORTANT]  
> Avant de pouvoir activer un utilisateur Lync Server 2013 pour la messagerie vocale hébergée, une stratégie de messagerie vocale hébergée qui s’applique à son compte d’utilisateur doit être déployée. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-hosted-voice-mail-policies.md">stratégies de messagerie vocale hébergée dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>Pour activer les utilisateurs pour la messagerie vocale hébergée

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez la cmdlet Set-CsUser pour configurer le compte d’utilisateur pour la messagerie vocale hébergée. Par exemple, exécutez :
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    L’exemple qui précède définit les paramètres suivants :
    
      - **HostedVoiceMail** permet d’acheminer les appels de la messagerie vocale d’un utilisateur vers la messagerie unifiée Exchange hébergée. Il signale également à Microsoft Lync 2013 l’indicateur d’appel de messagerie vocale.
    
      - **Identité** indique le compte d’utilisateur à modifier. Vous pouvez définir la valeur d’identité dans l’un des formats suivants :
        
          - l’adresse SIP de l’utilisateur ;
        
          - le nom d’utilisateur principal Active Directory ;
        
          - Nom de connexion au domaine de l’utilisateur \\ (par exemple, Contoso \\ kenmyer)
        
          - le nom complet des services de domaine Active Directory de l’utilisateur (par exemple, Ken Myer). Si vous utilisez le Display-Name en tant que valeur Identity, vous pouvez utiliser le \* caractère générique astérisque (). Par exemple, l’identité « \* Smith » renvoie tous les utilisateurs dont l' Display-Name se termine par la valeur de chaîne « Smith ».
        
        <div>
        

        > [!NOTE]  
        > Le nom de compte SAM Active Directory de l’utilisateur ne peut pas être utilisé comme valeur d’identité, car il n’est pas forcément unique dans la forêt.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

