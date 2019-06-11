---
title: 'Lync Server 2013: configuration des États de présence personnalisés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12083d1895f8e5191f15b43efaf2835faecdb5ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>Configuration des États de présence personnalisés dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-10_

Pour définir des États de présence personnalisés dans Lync 2013, créez un fichier de configuration de présence XML personnalisé, puis spécifiez son emplacement à l’aide des applets de technologie Lync Server Management Shell **New-CSClientPolicy** ou **Set-CSClientPolicy** avec le paramètre CustomStateURL.

Les fichiers de configuration sont dotés des propriétés suivantes:

  - Les statuts de présence personnalisés peuvent être configurés avec les indicateurs de présence disponible, occupé et ne pas déranger.

  - L’attribut Availability détermine quel indicateur de présence est associé au texte d’état de l’état personnalisé. Dans l’exemple ci-dessous, le texte d’État qui travaille à partir de l’accueil est affiché à droite de l’indicateur de présence vert (disponible).

  - La longueur maximale du texte de statut est de 64 caractères.

  - Vous pouvez ajouter un maximum de quatre États de présence personnalisés.

  - Le paramètre CustomStateURL spécifie l’emplacement du fichier de configuration. Dans Lync 2013, le mode haute sécurité SIP est activé par défaut, de sorte que vous devrez stocker le fichier de configuration de présence personnalisée sur un serveur Web sur lequel HTTPs est activé. Dans le cas contraire, les clients 2013 Lync ne seront pas en mesure de s’y connecter. Par exemple, une adresse valide est `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.

<div>


> [!NOTE]  
> Même si cette option n’est pas recommandée dans un environnement de production, vous pouvez tester un fichier de configuration situé sur un partage de fichiers non HTTPs à l’aide du paramètre de Registre EnableSIPHighSecurityMode pour désactiver le mode haute sécurité SIP sur le client. Vous pouvez ensuite utiliser le paramètre de Registre CustomStateURL pour spécifier un emplacement non HTTP pour le fichier de configuration. Notez que Lync 2013 respecte les paramètres de registre de Lync 2010, mais la ruche du registre a été mise à jour. Vous pouvez créer les paramètres de Registre comme suit: 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>Type: DWORD</P>
> <P>Données de la valeur: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>Type: chaîne (REG_SZ)</P>
> <P>Données de la valeur (exemples)\\: file://lspool. Corp. contoso. com\LSFileShare\ClientConfigFolder\Presence.xml ou file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.Xml</P></LI></UL>



</div>

Localisez votre état de présence personnalisé en spécifiant un ou plusieurs schémas d’ID de paramètres régionaux (LCID) dans le fichier de configuration XML. L’exemple plus loin dans cette rubrique montre la localisation en anglais-États-Unis (1033), Norvégien-Bokmål (1044), français-France (1036) et turc (1055). Pour obtenir une liste de LCID, voir ID de paramètres régionaux attribués <http://go.microsoft.com/fwlink/p/?linkid=157331>par Microsoft à.

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a>Pour ajouter des États de présence personnalisés à Lync 2013

1.  Créez un fichier de configuration XML qui utilise le format de l’exemple suivant:
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  Enregistrez le fichier de configuration XML sur un serveur Web avec HTTPs activé. Dans cet exemple, le fichier est nommé Presence. xml et enregistré à l’emplacement https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.

3.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Dans Lync Server Management Shell, définissez l’emplacement de votre fichier de configuration XML à l’aide d’une commande similaire à ce qui suit:
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  Utilisez l’applet de passe **Grant-CSClientPolicy** pour affecter cette nouvelle stratégie aux utilisateurs.

Pour plus d’informations, reportez-vous à [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) et [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) dans la documentation Lync Server Management Shell.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Par défaut, la mise à&nbsp;jour des stratégies client et des paramètres de Lync Server 2013 toutes les trois heures.</P>
> <LI>
> <P>Si vous voulez continuer à utiliser les paramètres de stratégie de groupe des versions précédentes, telles que CustomStateURL, Lync 2013 reconnaîtra les paramètres s’ils se trouvent dans la nouvelle ruche du registre de la stratégie (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync). En revanche, les stratégies de client serveur sont prioritaires.</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

