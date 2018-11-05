---
title: Configuration des états de présence personnalisés
TOCTitle: Configuration des états de présence personnalisés
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398997(v=OCS.15)
ms:contentKeyID: 53095545
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des états de présence personnalisés

 

_**Dernière rubrique modifiée :** 2016-12-08_

Pour définir des statuts de présence personnalisés dans Lync 2013, créez un fichier XML de configuration de présence personnalisé, puis spécifiez son emplacement à l’aide de l’applet de commande Lync Server Management Shell**New-CSClientPolicy** ou **Set-CSClientPolicy** avec le paramètre CustomStateURL.

Les fichiers de configuration comportent les propriétés suivantes :

  - Les statuts de présence personnalisés peuvent être configurés à l’aide des indicateurs de présence Disponible, Occupé(e) et Ne pas déranger.

  - L’attribut de disponibilité détermine l’indicateur de présence associé au texte du statut personnalisé. Dans l’exemple présenté plus loin dans cette rubrique, le texte de statut Travaille à la maison s’affiche à droite de l’indicateur de présence vert (Disponible).

  - La longueur maximale du texte de statut est de 64 caractères.

  - Vous pouvez ajouter jusqu’à quatre statuts de présence personnalisés.

  - Le paramètre CustomStateURL indique l’emplacement du fichier de configuration. Dans Lync 2013, le mode de sécurité élevée SIP étant activé par défaut, vous devrez stocker le fichier de configuration de présence personnalisé sur un serveur web sur lequel le protocole HTTPS est activé. Dans le cas contraire, les clients Lync 2013 ne pourront pas s’y connecter. Exemple d’adresse valide : `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.

> [!NOTE]  
> Bien que cela ne soit pas recommandé dans un environnement de production, vous pouvez tester un fichier de configuration situé sur un partage de fichiers non-HTTPS en utilisant le paramètre de Registre EnableSIPHighSecurityMode pour désactiver le mode de sécurité élevée SIP sur le client. Vous pouvez ensuite utiliser le paramètre de Registre CustomStateURL pour spécifier un emplacement non-HTTPS pour le fichier de configuration. Notez que Lync 2013 honore les paramètres de Registre Lync 2010, mais que la ruche de Registre a été mise à jour. La création des paramètres du Registre s’effectuerait comme suit :
> <ul>
> <li><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</p>
> <p>Type : DWORD</p>
> <p>Données de la valeur : 0</p></li><li><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</p>
> <p>Type : String (REG_SZ)</p>
> <p>Données de la valeur (exemples) : file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml ou file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</p></li></ul>

Localisez votre statut de présence personnalisé en spécifiant un ou plusieurs schémas d’ID locaux (LCID) dans le fichier XML de configuration. L’exemple présenté plus loin dans cette rubrique montre une localisation en Anglais - États-Unis (1033), Norvégien - Bokmål (1044), Français - France (1036) et Turc (1055). Pour obtenir la liste des LCID, voir les ID locaux assignés par Microsoft à l’adresse <http://go.microsoft.com/fwlink/?linkid=157331>.

## Pour ajouter des statuts de présence personnalisés dans Lync 2013

1.  Créez un fichier de configuration XML utilisant le format de l’exemple suivant :
    
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

2.  Enregistrez le fichier de configuration XML sur un serveur web sur lequel le protocole HTTPS est activé. Dans cet exemple, le fichier se nomme Presence.xml et est enregistré à l’emplacement https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.

3.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Dans le Lync Server Management Shell, spécifiez l’emplacement de votre fichier XML de configuration à l’aide d’une commande de type :
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  Utilisez l’applet de commande **Grant-CSClientPolicy** pour assigner cette nouvelle stratégie aux utilisateurs.

Pour plus d’informations, voir [New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy) et [Grant-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientPolicy) dans la documentation Lync Server Management Shell.

> [!NOTE]  
> <ul>
> <li><p>Par défaut, Lync Server 2013 met à jour les stratégies et les paramètres du client toutes les trois heures.</p></li>
> <li><p>Si vous souhaitez continuer à utiliser des paramètres de stratégie de groupe des versions précédentes, tels que CustomStateURL, Lync 2013 reconnaîtra les paramètres s’ils se trouvent dans la nouvelle ruche de Registre de stratégies (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync). Cependant, les stratégies du client basées sur serveur sont prioritaires.</p></li></ul>

