---
title: Configuration du magasin de contacts personnels sur les ordinateurs clients
TOCTitle: Configuration du magasin de contacts personnels sur les ordinateurs clients
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49891596
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du magasin de contacts personnels sur les ordinateurs clients

 

_**Dernière rubrique modifiée :** 2016-12-08_

Si vous intégrez Microsoft Lync Server 2013 et Microsoft Exchange Server 2013, il vous est conseillé de configurer le magasin de contacts personnels sur tout ordinateur client exécutant Microsoft Lync 2010. Vous devez en particulier configurer Lync pour que Exchange soit utilisé comme magasin de contacts personnels et, en même temps, vous assurer que les utilisateurs ne peuvent pas passer outre cette décision. Vous pouvez faire cela en créant et en configurant une valeur Registre sur chaque ordinateur client.

Notez que ceci n'est pas obligatoire sur les ordinateurs exécutant Lync 2013.

Pour configurer cette valeur sur un ordinateur unique, procédez comme suit :

1.  Sur l’ordinateur client, cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **Exécuter**, tapez regedit, puis appuyez sur Entrée.

3.  Dans l’Éditeur du Registre, développez **HKEY\_LOCAL\_MACHINE**, **Software**, **Policies**, **Microsoft**, puis **Communicator**.

4.  Cliquez avec le bouton droit sur **Communicator**, pointez sur **Nouveau**, puis cliquez sur **Valeur DWORD (32 bits)**.

5.  Une fois la nouvelle valeur créée, tapez **PersonalContactStoreOverride**, puis appuyez sur Entrée pour renommer la valeur.

6.  Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’Éditeur du Registre.

Si vous devez effectuer le même changement sur plusieurs ordinateurs, vous pouvez le faire en créant un objet Stratégie de groupe personnalisé. Pour plus d’informations, voir la documentation concernant la Stratégie de groupe à l’adresse [http://go.microsoft.com/fwlink/?linkid=268543\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268543%26clcid=0x40c).

