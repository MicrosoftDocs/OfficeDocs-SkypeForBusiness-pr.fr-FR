---
title: 'Lync Server 2013 : afficher les paramètres de configuration de réunion'
description: 'Lync Server 2013 : afficher les paramètres de configuration de réunion.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190b9d331a8cd0a08e17c482dbc3b0bc27590003
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576400"
---
# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a>Afficher les paramètres de configuration de réunion dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Dans le panneau de configuration Lync Server 2013, utilisez le paramètre configuration de la réunion pour contrôler la façon dont les réunions sont implémentées dans votre déploiement. Cela inclut les configurations de réunion suivantes :

  - Une configuration globale qui est créée par défaut lorsque vous déployez Lync Server 2013.

  - Des configurations facultatives aux niveaux du site et de l’utilisateur que vous pouvez créer et utiliser pour spécifier la façon dont les réunions sont implémentées pour des sites ou des utilisateurs spécifiques.

<div>

## <a name="to-view-meeting-configuration-settings"></a>Pour afficher les paramètres de configuration de réunion :

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **Conférence**, puis cliquez sur **Configuration de la réunion**.

4.  Dans la page **Configuration de la réunion**, cliquez sur la configuration de réunion que vous voulez afficher.

5.  Dans **Modifier le filtre de fichiers**, cochez la case **Afficher les détails…**
    
    **Modifier la configuration de \<policy\> la réunion-** ouvre les paramètres de la stratégie sélectionnée. Pour plus d’informations sur la configuration des paramètres, voir [créer ou modifier une collection de paramètres de configuration de réunion dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration de réunion à l’aide des applets de commande Windows PowerShell

Les paramètres de configuration de réunion peuvent être affichés à l’aide de Windows PowerShell et de l’applet de commande Get-CsMeetingConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-meeting-configuration-information"></a>Pour afficher les informations de configuration de réunion

  - Pour afficher des informations sur tous vos paramètres de configuration de réunion, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsMeetingConfiguration
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

