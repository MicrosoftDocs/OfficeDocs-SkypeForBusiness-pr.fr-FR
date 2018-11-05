---
title: "Lync Server 2013 : Déf. et conf. d’une top. dans le gén. de top."
TOCTitle: Définition et configuration d’une topologie dans le générateur de topologie
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398788(v=OCS.15)
ms:contentKeyID: 49298251
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition et configuration d’une topologie dans le générateur de topologie pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

L’exécution du Générateur de topologie pour définir une nouvelle topologie ou en modifier une existante ne nécessite pas d’être membre d’un groupe d’administrateurs locaux ou de domaines privilégiés. Le Générateur de topologie vous guide tout au long des étapes nécessaires à la définition de la topologie d’un pool frontal Enterprise Edition ou Standard Edition, selon la configuration requise.

Vous devez utiliser le Générateur de topologie pour terminer et publier la topologie avant de pouvoir installer Lync Server 2013 sur des serveurs. La procédure suivante intègre les étapes requises pour définir une nouvelle topologie.

## Pour définir une topologie

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans le Générateur de topologie, sélectionnez **Nouvelle topologie** . Sélectionnez un emplacement et définissez un nom de fichier pour enregistrer la topologie. Attribuez au fichier de la topologie un nom explicite et validez l’extension par défaut .tbxml. Cliquez sur **OK** .

3.  Accédez à l’emplacement d’enregistrement du nouveau fichier XML de topologie, entrez un nom de fichier, puis cliquez sur **Enregistrer** .

4.  À la page **Définir le domaine principal** , entrez le nom du domaine SIP principal de votre organisation, puis cliquez sur **Suivant** .

5.  À la page **Spécifier d’autres domaines pris en charge** , entrez les noms des domaines supplémentaires, le cas échéant, et cliquez sur **Suivant** .

6.  À la page **Définir le premier site** , entrez un nom et une description du premier site, puis cliquez sur **Suivant** .

7.  À la page **Spécifier les détails du site** , tapez les informations sur l’emplacement, puis cliquez sur **Suivant** .

8.  Dans la page **Nouvelle topologie correctement définie**, veillez à cocher la case **Ouvrir l’Assistant Nouveau serveur frontal à la fermeture de cet Assistant**, puis cliquez sur **Terminer**.

Après avoir défini et enregistré la topologie, utilisez l’Assistant Nouveau serveur frontal pour définir un pool frontal ou un serveur Standard Edition pour votre site. Pour plus d’informations, reportez-vous à [Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).

