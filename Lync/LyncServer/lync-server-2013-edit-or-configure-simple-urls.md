---
title: 'Lync Server 2013 : Modification ou configuration des URL simples'
TOCTitle: Modification ou configuration des URL simples
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398063(v=OCS.15)
ms:contentKeyID: 49296047
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification ou configuration des URL simples dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-04_

Pour effectuer cette procédure, il n’est pas nécessaire d’appartenir à un groupe d’administrateurs local ou de domaines privilégiés. Vous devez simplement ouvrir une session sur un ordinateur en tant qu’utilisateur standard.

Lync Server 2013 utilise des URL simples pour acheminer les appels internes et externes vers les services sur le serveur frontal ou directeur, s’il a été déployé. Pour plus d’informations sur les URL simples, reportez-vous à [Planification des URL simples dans Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) dans la documentation de planification. Vous pouvez sélectionner le format de vos URL simples grâce à diverses options. Pour plus d’informations sur ces options, reportez-vous à [Enregistrements DNS requis pour les URL simples dans Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) dans la documentation de planification.

Par défaut, le format des URL simples est le suivant (par exemple, l’URL simple dial-in) : https://dialin.\<Domaine SIP\>

## Pour configurer des URL simples

1.  Dans Générateur de topologie, cliquez avec le bouton droit sur le nœud **Lync Server**, puis cliquez sur **Modifier les propriétés**.

2.  Dans le volet **URL simples** , sélectionnez **URL d’accès téléphonique :** (Dial-In) ou **URL de réunion :** (Meet) pour modifier l’URL, puis cliquez sur **Modifier l’URL** .

3.  Mettez à jour l’URL avec la valeur souhaitée, puis cliquez sur **OK** pour l’enregistrer. Dans l’exemple présenté ici, l’URL Dial-in a été modifiée comme suit : https://pool01.contoso.net/dialin.

4.  Modifiez l’URL Meet en procédant de la même manière, si nécessaire.

## Pour définir l’URL simple Admin facultative

1.  Dans Générateur de topologie, cliquez avec le bouton droit sur le nœud **Lync Server**, puis cliquez sur **Modifier les propriétés**.

2.  Dans la zone **URL d’accès administratif** , entrez l’URL simple vous donnant accès au Panneau de configuration Lync Server 2013 à des fins d’administration, puis cliquez sur **OK** .
    
    > [!TIP]  
    > Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL Admin. L’option la plus simple est <strong>https://admin.</strong> <em>&lt;domaine&gt;</em> .    
    > [!IMPORTANT]  
    > Si vous modifiez une URL simple après son déploiement, sachez que cette modification risque d’altérer les enregistrements et les certificats DNS (Domain Name System) pour les URL simples. Si la modification altère la base d’une URL simple, vous devez également modifier les enregistrements et les certificats DNS. Par exemple, si vous modifiez https://lync.contoso.com/Meet de sorte qu’elle devienne https://meet.contoso.com, l’URL de base change, lync.contoso.com est remplacé par meet.contoso.com. Par conséquent, vous devez modifier les enregistrements et les certificats DNS de sorte qu’ils fassent référence à meet.contoso.com. Si vous avez modifié l’URL simple afin que https://lync.contoso.com/Meet devienne https://lync.contoso.com/Meetings, l’URL de base lync.contoso.com ne change pas. Il n’est donc pas nécessaire de modifier les enregistrements ou les certificats DNS. Cependant, lorsque vous modifiez un nom d’URL simple, vous devez exécuter l’applet de commande <strong>Enable-CsComputer</strong> sur chaque directeur et serveur frontal pour enregistrer la modification.

## Voir aussi

#### Concepts

[Planification des URL simples dans Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

