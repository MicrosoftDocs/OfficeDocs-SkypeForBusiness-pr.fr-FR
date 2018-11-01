---
title: Changer l’URL des services Web dans Lync Server 2013
TOCTitle: Changer l’URL des services Web dans Lync Server 2013
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520992(v=OCS.15)
ms:contentKeyID: 49297150
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Changer l’URL des services Web dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-11-16_

Lorsque vous configurez vos pools frontaux et vos serveurs Standard Edition, vous avez la possibilité de configurer un nom de domaine complet (FQDN) de batterie de serveurs web externes et des ports associés. Si vous n’avez pas configuré cette URL lorsque vous avez exécuté l’Assistant Déploiement de Lync Server, vous devez définir manuellement ces paramètres. Un administrateur n’a généralement pas besoin de modifier ces paramètres, puisqu’il s’agit des valeurs recommandées et des ports par défaut.

> [!NOTE]  
> La capture d'écran suivante ayant été effectuée lors de la configuration d'un serveur Standard Edition, l'option Remplacer le nom de domaine complet est désactivée. Cette option est activée lors de la configuration d'un serveur Enterprise Edition dans un pool frontal.

![Modifier les paramètres de pool des services Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Modifier les paramètres de pool des services Web")

## Pour configurer des services Web

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

3.  Dans le Générateur de topologie, dans l’arborescence de la console sous **Serveurs frontaux Standard Edition**, **Pools frontaux Enterprise Edition** et **Pools directeurs**, sélectionnez le nom du pool. Cliquez avec le bouton droit sur le nom, cliquez sur **Modifier les propriétés**, puis cliquez sur **Services web**.

4.  Ajoutez ou modifiez le **Nom de domaine complet (FQDN) des services web externes**, puis cliquez sur **OK**.
    
    > [!WARNING]  
    > Si vous installez plus d’un pool de serveurs frontaux ou serveur frontal, le nom de domaine complet des services web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services web externes d’un serveur frontal en tant que <strong>pool01.contoso.com</strong>, vous ne pouvez pas utiliser ce nom <strong>pool01.contoso.com</strong> pour un autre pool de serveurs frontaux ou serveur frontal. Si vous déployez aussi des directeurs, le nom de domaine complet des services web externes défini pour un directeur ou un pool de directeurs doit être différent de tout autre directeur ou pool de directeurs et de tout pool de serveurs frontaux ou serveur frontal existant.

5.  Vérifiez que les ports d’écoute et les ports publiés sont correctement configurés pour votre environnement.

6.  Répétez ces étapes pour tous les serveurs Standard Edition, pools frontaux et pools directeurs dans votre environnement.

7.  Dans l’arborescence de la console, cliquez sur **Lync Server 2013** puis, dans le volet **Actions**, cliquez sur **Publier la topologie**.

Vous devez respecter quelques conditions préalables lorsque vous configurez les ports d’écoute et de publication :

  - Les ports d’écoute présentés sont les ports configurés pour Internet Information Server (IIS) sur chaque serveur frontal.

  - Les ports d’écoute internes et externes doivent être différents pour IIS. En ce qui concerne les ports d’écoute externes, ils sont généralement identiques, car l’un représente le programme d’équilibrage de la charge matérielle pour le trafic web interne et l’autre représente le serveur proxy inverse pour le trafic web externe.

  - Vous pouvez remplacer les services web internes d’un pool de serveurs frontaux, d’un directeur ou d’un pool de directeurs, puis définir votre propre nom de domaine complet.
    
    > [!WARNING]  
    > Si vous choisissez de remplacer le nom des services web internes par un nom de domaine complet personnalisé, chaque nom de domaine complet doit être distinct des autres noms de pool de serveurs frontaux, directeur ou pool de directeurs.

  - Les ports publiés doivent être configurés sur le proxy inverse ou le programme d’équilibrage de la charge matérielle en tant que ports d’écoute.

  - Pour un pool frontal (non présenté dans l’exemple), le nom de domaine complet (FQDN) du pool SIP interne doit être différent du nom de domaine complet (FQDN) des services web internes, car le trafic web passe par le programme d’équilibrage de la charge matérielle et le trafic du pool SIP interne passe par le programme d’équilibrage de la charge DNS. Cette condition préalable doit être respectée.

  - Un déploiement de Lync Server Standard Edition n’a pas besoin d’un remplacement du nom de domaine complet des services web internes, ou ne l’autorise pas, car la charge de ce serveur ne peut pas être équilibrée.

  - Si vous disposez d’un programme d’équilibrage de la charge matérielle dans votre environnement et que vous l’utilisez pour le trafic web et SIP interne, le Générateur de topologie ne peut pas faire la distinction.
    
    Les noms de domaine complets des services Web doivent être clairement différenciés les uns des autres pour mieux faire en sorte que la redirection des URL pointe les clients vers le serveur approprié. Par exemple, si vous avez deux noms de domaine complets, vous pouvez envisager de nommer meeting.contoso.com l'un et conferencing.contoso.com l'autre. Vous risquez éventuellement de rencontrer des problèmes de redirection si vous avez des noms de domaine complets avec d'autres noms similaires, tels que meet1.contoso.com et meet2.contoso.com.

Les services web externes fonctionnent conjointement avec un proxy inverse dans le réseau de périmètre. Il fournit aux clients un accès externe à l’aide de ces services web. Les noms de domaine complets configurés ici sont envoyés aux clients quand ils se connectent et sont utilisés pour établir une connexion HTTPS au proxy inverse en cas de connexion à distance. Le serveur proxy inverse transfère le nom de domaine complet des services web externes à un appareil d’équilibrage de charge interne ou directement au pool. Le serveur proxy doit pouvoir résoudre le nom de domaine complet des services web externes en adresse IP du serveur web interne. Le nom de domaine complet des services web externes doit pouvoir être résolu sur le réseau Internet public.

Si votre serveur interne est un serveur Standard Edition, le nom de domaine complet (FQDN) interne est le nom de domaine complet (FQDN) du serveur Standard Edition. Si votre serveur interne est un pool frontal, le nom de domaine complet (FQDN) est une adresse IP virtuelle (VIP) du programme d’équilibrage de la charge matérielle, qui équilibre la charge des serveurs de la batterie de serveurs web internes. Un programme d’équilibrage de la charge matérielle est nécessaire dans un pool frontal comportant plusieurs serveurs Enterprise Edition. Un programme d’équilibrage de la charge n’est pas nécessaire pour un serveur Standard Edition ou un seul serveur frontal Enterprise Edition.

