---
title: 'Lync Server 2013 : affichage des informations des paramètres de configuration de Lync Phone Edition'
description: 'Lync Server 2013 : afficher les informations des paramètres de configuration de Lync Phone Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62719b24920ee72a92b2f80498d5ea2a59288c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576430"
---
# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>Afficher les informations des paramètres de configuration de Lync Phone Edition dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez afficher des informations de configuration sur les appareils exécutant Lync Phone Edition. Les informations sont classées dans des collections. Lorsque vous installez Lync Server, vous obtenez une collection de paramètres Lync Phone Edition qui s’appliquent à tous les appareils exécutant Lync Phone Edition dans votre déploiement. Vous pouvez également créer de nouvelles collections de paramètres pour un site en particulier. Les paramètres du site ont priorité sur les paramètres globaux. Chaque collection de paramètres se compose d’un nom, de l’étendue (globale ou de site), du paramètre de sécurité SIP, du niveau de journalisation, du niveau de qualité de service de la voix (QoS), du paramètre de verrouillage du téléphone et des détails de verrouillage du téléphone, c’est-à-dire la longueur minimale du code confidentiel de déverrouillage et le délai avant le verrouillage automatique du téléphone.

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>Pour afficher les informations de configuration des appareils exécutant Lync Phone Edition

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration du périphérique**.

4.  Dans la page **Configuration du périphérique**, cliquez sur la collection de paramètres sur laquelle vous souhaitez afficher des informations. Le nom, l’étendue, le paramètre de sécurité SIP, le niveau de qualité de service de la voix et le paramètre de verrouillage du téléphone sont répertoriés dans la page principale. Pour afficher le niveau de journalisation et les détails de verrouillage du téléphone, cliquez sur le menu **Edition**, puis sur **Afficher les détails**.

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration de Lync Phone Edition à l’aide des applets de commande Windows PowerShell

Vous pouvez afficher les paramètres de configuration de Lync Phone Edition à l’aide de Lync Server Management Shell et de la cmdlet **Get-CsUCPhoneConfiguration** . Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>Pour afficher les informations de configuration de Lync Phone Edition

  - Pour afficher des informations sur tous les paramètres de configuration de Lync Phone Edition, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsUCPhoneConfiguration
    
    La commande renvoie les informations suivantes :
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

Pour plus d’informations, consultez la rubrique [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification d’une collection de paramètres de configuration Lync Phone Edition dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Supprimer une collection existante de paramètres de configuration Lync Phone Edition dans Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Configurer les paramètres de sécurité pour Lync Phone Edition dans Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Appliquer le verrouillage du téléphone dans Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

