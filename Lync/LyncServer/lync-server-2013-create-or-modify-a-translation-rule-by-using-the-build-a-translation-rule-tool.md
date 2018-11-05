---
title: "Créer ou mod. une règle de trad. à l’aide de l’outil Créer une règle de trad."
TOCtitle: "Créer ou mod. une règle de trad. à l’aide de l’outil Créer une règle de trad."
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412909(v=OCS.15)
ms:contentKeyID: 49298644
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer ou modifier une règle de traduction à l’aide de l’outil Créer une règle de traduction

 

_**Dernière rubrique modifiée :** 2012-10-05_

Suivez la procédure suivante si vous souhaitez définir une règle de traduction en entrant un ensemble de valeurs dans l’outil **Créer une règle de traduction** et en autorisant le Panneau de configuration Lync Server à générer le modèle correspondant et la règle de traduction pour vous. Vous pouvez également écrire manuellement une expression régulière pour définir le modèle correspondant et la règle de traduction. Pour plus d’informations, voir [Créer ou modifier manuellement une règle de traduction](lync-server-2013-create-or-modify-a-translation-rule-manually.md).

## Pour définir une règle à l’aide de l’outil Créer une règle de traduction

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Pour commencer à définir une règle de traduction, suivez les étapes dans [Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) jusqu’à l’étape 10 ou [Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) jusqu’à l’étape 9.

4.  Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.

5.  (Facultatif) Sous **Description**, entrez la description de la règle de traduction ; par exemple, **Appel longue distance international**.

6.  Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :
    
      - **Chiffres de début** : (Facultatif) Précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle. Par exemple, entrez **+** dans ce champ pour faire correspondre les numéros au format E.164 (commençant par un signe +).
    
      - **Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque. Par exemple, entrez **11** et sélectionnez l’option **Au moins** dans la liste déroulante pour faire correspondre les numéros dont la longueur est d’au minimum 11 chiffres.
    
      - **Chiffres à supprimer** : (Facultatif) Précisez le nombre de chiffres de début à supprimer. Par exemple, entrez **1** pour retirer le signe **+** au début du numéro.
    
      - **Chiffres à ajouter** : (Facultatif) Précisez les chiffres à ajouter aux numéros traduits. Par exemple, entrez **011** si vous souhaitez ajouter 011 aux numéros traduits au moment d’appliquer la règle.
    
    Les valeurs saisies dans ces champs sont reproduites dans les champs **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous appliquez les valeurs de l’exemple précédent, l’expression régulière obtenue dans le champ **Modèle à suivre** est :
    
    **^\\+(\\d{9}\\d+)$**
    
    Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits. Ce modèle comprend deux parties :
    
      - Une valeur (par exemple, **$1**) qui représente le nombre de chiffres dans le modèle correspondant.
    
      - (Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.
    
    Si vous utilisez les valeurs de l’exemple précédent, **011$1** apparaît dans le champ **Règle de traduction**.
    
    Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.

7.  Cliquez sur **OK** pour enregistrer la règle de traduction.

8.  Cliquez sur **OK** pour enregistrer la configuration de la jonction.

9.  Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]  
    > Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la modification de la configuration. Pour plus d’informations, voir <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> dans la documentation des opérations.

## Voir aussi

#### Tâches

[Créer ou modifier manuellement une règle de traduction](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Concepts

[Options globales du contournement de média dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)

