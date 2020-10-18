---
title: 'Lync Server 2013 : afficher les informations de stratégie de conférence'
description: 'Lync Server 2013 : afficher les informations sur la stratégie de conférence.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e463c500e48f4032c8dab3a3787715f7265be9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579430"
---
# <a name="view-conferencing-policy-information-in-lync-server-2013"></a>Afficher les informations de stratégie de conférence dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Dans le panneau de configuration Lync Server 2013, vous utilisez des stratégies de conférence pour contrôler la mise en œuvre de la Conférence dans votre déploiement. Parmi les stratégies de conférence se trouvent :

  - Stratégie globale créée par défaut lorsque vous déployez Lync Server 2013.

  - une stratégie facultative au niveau du site et au niveau de l’utilisateur que vous pouvez créer et utiliser pour spécifier la manière dont la conférence est implémentée pour des sites ou utilisateurs spécifiques.

<div>

## <a name="to-view-conferencing-policy-settings"></a>Pour voir les paramètres de stratégie de conférence

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.

4.  Sur la page **Stratégie de conférence**, double-cliquez sur la stratégie de conférence que vous voulez voir.

5.  Dans **Modifier le filtre de fichier**, sélectionnez la case à cocher **Afficher les détails…**.
    
    **Modifier la stratégie de \<policy\> Conférence-** ouvre les paramètres de la stratégie sélectionnée. Pour plus d’informations sur la configuration des paramètres, voir [Create or Modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a>Affichage des stratégies de conférence à l’aide des applets de commande Windows PowerShell

Les stratégies de conférence peuvent être visualisées à l’aide de Windows PowerShell et de l’applet de commande Get-CsConferencingPolicy. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-conferencing-policies"></a>Pour afficher les stratégies de conférence

  - Pour afficher des informations sur toutes vos stratégies de conférence, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsConferencingPolicy
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

