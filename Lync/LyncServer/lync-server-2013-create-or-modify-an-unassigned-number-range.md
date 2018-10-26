---
title: "Lync Server 2013 : Créa. ou modification d’une plage de numéros non attribués"
TOCTitle: Création ou modification d’une plage de numéros non attribués
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412748(v=OCS.15)
ms:contentKeyID: 49298356
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification d’une plage de numéros non attribués dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Appliquez l’une des procédures suivantes pour configurer des plages de numéros non attribués pour l’application d’annonce.

> [!IMPORTANT]  
> Avant de configurer la table des numéros non attribués, vous devez avoir défini une ou plusieurs annonces ou configuré un standard automatique de la messagerie unifiée Exchange.

## Pour configurer des numéros de téléphone non attribués à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Numéro non attribué**.

4.  Dans la page **Numéro non attribué**, effectuez l’une des opérations suivantes :
    
      - Pour créer une nouvelle plage de numéros, cliquez sur **Nouveau**. Dans **Nom**, tapez le nom de cette plage de numéros.
        
        > [!NOTE]  
        > Une fois que vous avez validé la nouvelle plage de numéros non attribués dans la base de données, vous ne pouvez plus modifier ce nom.    
      - Pour modifier une plage de numéros existante, tapez tout ou une partie du nom de la plage de numéros dans le champ de recherche. Dans la liste des plages de numéros résultante, cliquez sur celle voulue, cliquez sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans le premier champ **Plage de numéros**, tapez le numéro de début de plage, puis dans le second champ **Plage de numéros**, tapez le numéro de fin de la plage.
    
    > [!NOTE]  
    > <ul>    
    > <li><p>Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de celle-ci.</p></li>    
    > <li><p>Si le numéro de début ou de fin de plage inclut un numéro de poste, les numéros de début et de fin de plage doivent inclure un poste, et le numéro d’extension doit être le même pour les numéros de début et de fin de plage.</p></li>    
    > <li><p>Le numéro doit correspondre à l’expression régulière (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?. Cela implique que le numéro peut commencer par la chaîne tel: (si vous ne spécifiez pas cette chaîne, elle sera automatiquement ajoutée pour vous), un signe plus (+) et un chiffre de 1 à 9. Le numéro de téléphone peut comporter jusqu’à 17 chiffres et peut être suivi d’un poste au format ;ext= suivi du numéro de poste.</p></li>
    > </ul>


6.  Dans **Service d’annonce**, effectuez l’une des opérations suivantes :
    
      - Cliquez sur **Annonce**.
    
      - Cliquez sur **Messagerie unifiée Exchange**.

7.  Si, dans l’étape précédente, vous avez cliqué sur **Annonce**, procédez comme suit :
    
    1.  Sous **Nom de domaine complet du serveur de destination**, cliquez sur **Sélectionner**, cliquez sur l’ID de service du service Application qui exécute l’application d’annonce devant gérer les appels entrants destinés à cette plage de numéros non attribués, puis cliquez sur **OK**.
    
    2.  Dans **Annonce**, cliquez sur l’annonce à associer à cette plage de numéros non attribués.

8.  Si, dans l’étape précédente, vous avez cliqué sur **Messagerie unifiée Exchange**, sous **Numéro de téléphone du standard automatique**, cliquez sur **Sélectionner**, puis sur le numéro de téléphone devant être utilisé par cette plage de numéros non attribués et cliquez sur **OK**.

9.  Cliquez sur **OK**.

10. Dans la page **Numéro non attribué**, vérifiez que les plages de numéros non attribués s’affichent dans l’ordre voulu. Pour déplacer une plage dans la table, cliquez sur un ou plusieurs noms consécutifs dans la liste de plages, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!TIP]  
    > Lync Server analyse la table de haut en bas et utilise la première plage correspondant au numéro non attribué. Si des plages se chevauchent et qu’une plage spécifie une action de dernier recours, vérifiez qu’elle se trouve en bas de la liste.

11. Une fois que vous disposez des plages de numéros non attribués dans l’ordre souhaité, cliquez sur **Valider tout**.

## Pour configurer des numéros de téléphone non attribués à l’aide du Windows PowerShell

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Utilisez **New-CsUnassignedNumber** pour créer une plage de numéros non attribués. Utilisez **Set-CsUnassignedNumber** pour modifier une plage de numéros non attribués existante.
    
    > [!TIP]  
    > Si des plages se chevauchent et vous souhaitez qu’elles soient appliquées dans un ordre spécifique, incluez le paramètre Priority. La plage dont la priorité est la plus élevée sera appliquée à l’appel.    
    Dans la ligne de commande, effectuez l’une des opérations suivantes :
    
      - Pour créer une plage de numéros pour un service Annonces, exécutez :
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - Ou pour créer une plage de numéros pour le standard automatique de messagerie unifiée Exchange, exécutez :
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    Exemple :
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    Ou
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    L’exemple suivant montre comment modifier les numéros d’une plage de numéros non attribués existante :
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

## Voir aussi

#### Tâches

[Supprimer une plage de numéros non attribués dans Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)  

#### Autres ressources

[New-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUnassignedNumber)

