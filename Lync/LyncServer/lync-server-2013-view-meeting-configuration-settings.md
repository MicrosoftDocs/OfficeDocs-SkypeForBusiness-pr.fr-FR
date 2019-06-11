---
title: 'Lync Server 2013: afficher les paramètres de configuration de la réunion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b3107045d62b244c7ee89dbb47228bc5dd72583
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a>Afficher les paramètres de configuration de la réunion dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Dans Lync Server 2013 panneau de configuration, vous utilisez le paramètre de configuration de la réunion pour contrôler l’implémentation des réunions dans votre déploiement. Cela inclut les configurations de réunion suivantes:

  - Configuration globale créée par défaut lors du déploiement de Lync Server 2013.

  - Configurations facultatives de niveau de site et de niveau utilisateur que vous pouvez créer et utiliser pour spécifier le mode d’implémentation des réunions pour des sites ou des utilisateurs spécifiques.

<div>

## <a name="to-view-meeting-configuration-settings"></a>Pour afficher les paramètres de configuration de la réunion

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence** , puis sur Configuration de la **réunion**.

4.  Dans la page **Configuration de la réunion**, cliquez sur la configuration de réunion à afficher.

5.  Dans **modifier le filtre de fichier**, sélectionnez l’option **afficher les détails...** case à cocher.
    
    **Modifier la configuration de \<la\> réunion: une stratégie** s’ouvre et affiche les paramètres de la stratégie sélectionnée. Pour plus d’informations sur la configuration des paramètres, voir [créer ou modifier un ensemble de paramètres de configuration de réunion dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration de la réunion à l’aide des cmdlets Windows PowerShell

Les paramètres de configuration de réunion peuvent être affichés à l’aide de Windows PowerShell et de l’applet de passe Get-CsMeetingConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-view-meeting-configuration-information"></a>Pour afficher les informations de configuration de la réunion

  - Pour afficher des informations sur l’ensemble des paramètres de configuration de la réunion, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée:
    
        Get-CsMeetingConfiguration
    
    Vous obtiendrez des indications semblables à ceci :
    
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

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

