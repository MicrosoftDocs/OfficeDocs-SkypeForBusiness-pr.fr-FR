---
title: 'Lync Server 2013 : Activation des utilisateurs pour la messagerie vocale hébergée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45872df26989d8d264ce77406bfbce86f321ccf8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Activation des utilisateurs pour la messagerie vocale hébergée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-24_

Suivez la procédure pour activer les utilisateurs de Lync Server 2013 pour la messagerie vocale sur un service de messagerie unifiée Exchange hébergé.

Pour plus d’informations, reportez-vous à la rubrique [gestion des utilisateurs Exchange hébergés dans Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) dans la documentation de planification.

Pour plus d’informations sur l’applet [de connexion Set-Csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , voir la documentation Lync Server Management Shell.

<div>


> [!IMPORTANT]  
> Pour 2013 que l’utilisateur de la messagerie vocale hébergée puisse être activé, une stratégie de messagerie vocale hébergée qui s’applique à son compte d’utilisateur doit être déployée. Pour plus d’informations, reportez-vous <A href="lync-server-2013-hosted-voice-mail-policies.md">à stratégies de messagerie vocale hébergées dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>Pour autoriser les utilisateurs à utiliser la messagerie vocale hébergée

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de cmdlet Set-CsUser pour configurer le compte d’utilisateur pour la messagerie vocale hébergée. Par exemple, exécutez :
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    L’exemple qui précède définit les paramètres suivants :
    
      - **HostedVoiceMail** permet d’acheminer les appels de messagerie vocale d’un utilisateur vers la messagerie unifiée Exchange hébergée. Il signale également Microsoft Lync 2013 pour allumer l’indicateur «appel de la messagerie vocale».
    
      - **Identité** indique le compte d’utilisateur à modifier. La valeur IDENTITY peut être spécifiée en utilisant l’un des formats suivants:
        
          - Adresse SIP de l’utilisateur
        
          - Nom d’utilisateur principal d’Active Directory de l’utilisateur
        
          - Le nom de connexion\\au domaine de l’utilisateur (par\\exemple, contoso kenmyer);
        
          - Nom d’affichage des services de domaine Active Directory de l’utilisateur (par exemple, Ken Myer). Si vous utilisez le nom d’affichage comme valeur d’identité, vous pouvez utiliser le caractère\*générique astérisque (). Par exemple, l’identité «\* Smith» renvoie tous les utilisateurs qui ont un nom d’affichage qui se termine par la valeur de chaîne «Smith».
        
        <div>
        

        > [!NOTE]  
        > Le nom de compte SAM-nom Active Directory de l’utilisateur ne peut pas être utilisé en tant que valeur d’identité, car le nom de compte SAM n’est pas nécessairement unique dans la forêt.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

