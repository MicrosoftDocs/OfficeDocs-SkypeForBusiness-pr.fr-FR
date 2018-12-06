---
title: Créer ou modifier manuellement une règle de traduction
TOCTitle: Créer ou modifier manuellement une règle de traduction
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398099(v=OCS.15)
ms:contentKeyID: 49296112
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer ou modifier manuellement une règle de traduction

 

_**Dernière rubrique modifiée :** 2012-08-06_

Effectuez cette procédure si vous voulez définir une règle de traduction en écrivant une expression régulière pour le modèle correspondant et la règle de traduction. Vous pouvez également entrer un ensemble de valeurs dans l’outil **Créer une règle de traduction** et générer automatiquement le modèle correspondant et la règle de traduction à l’aide du Panneau de configuration Lync Server . Pour plus d’informations, voir [Créer ou modifier une règle de traduction à l’aide de l’outil Créer une règle de traduction](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).

## Pour définir une règle de traduction manuellement

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Pour commencer à définir une règle de traduction, suivez les étapes dans [Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) jusqu’à l’étape 10 ou [Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) jusqu’à l’étape 9.

4.  Dans le champ **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.

5.  (Facultatif) Dans **Description**, entrez la description de la règle de traduction, par exemple **Appel longue distance international**.

6.  Cliquez sur **Modifier** au bas de la section **Créer une règle de traduction**.

7.  Entrez ce qui suit dans **Taper une expression régulière** :
    
      - Dans **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.
    
      - Dans **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.
    
    Par exemple, si vous entrez **^\\+(\\d{9}\\d+)$** dans **Suivre ce modèle** et **011$1** dans **Règle de traduction**, la règle traduira le numéro +441235551010 comme suit, 011441235551010.

8.  Cliquez sur **OK** pour enregistrer la règle de traduction.

9.  Cliquez sur **OK** pour enregistrer la configuration de la jonction.

10. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]  
    > À chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la modification de la configuration. Pour plus d’informations, voir <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> dans la documentation des opérations.

## Voir aussi

#### Tâches

[Créer ou modifier une règle de traduction à l’aide de l’outil Créer une règle de traduction](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Concepts

[Options globales du contournement de média dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)

