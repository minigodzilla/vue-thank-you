<template>
	<div class="viewer-header">
		<h1>Collaborative Camera Roll</h1>
		<h2>295 photos, taken by all of you!</h2>
	</div>
	<div class="viewer">
		<div class="box" v-for="photo in photos" :class="photo.orientation" :key="photo.name">
			<img :src="photo" />
		</div>
		<div id="anchor"></div>
	</div>
</template>

<style lang="scss">
.viewer {
	display: flex;
	flex-wrap: wrap;
	padding: 0 5%;

	@keyframes pop {
		0% {
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}

	.box {
		position: relative;
		width: 25%;
		height: 22.5vw;
		display: flex;
		align-items: center;
		justify-content: center;
		animation-name: pop;
		animation-fill-mode: both;
		animation-timing-function: ease-out;
		animation-duration: 750ms;
		animation-delay: 1s;
		// flex-shrink: 0;

		@media only screen and (max-width: 567px) {
			width: 50%;
			height: 48vw;
		}

		&.portrait img,
		&.landscape img {
			padding: 2%;
			background-color: #dfd3c2;
			box-shadow: 0.5vw 0.5vw 0.5vw rgba(0, 0, 0, 0.5);
		}

		&.portrait {
			img {
				width: auto;
				height: 90%;
			}
		}

		&.landscape {
			img {
				width: 90%;
				height: auto;
			}
		}
	}
}
</style>

<script>
export default {
	data() {
		return this.initialState();
	},
	methods: {
		initialState() {
			return {
				photos: [
					'https://p.jennandsteve.ca/upload/23l1fx1lyf.jpg',
					'https://p.jennandsteve.ca/upload/cmx1mb1wq8.jpg',
					'https://p.jennandsteve.ca/upload/cnx6b3rcst.jpg',
					'https://p.jennandsteve.ca/upload/np5wa7ldiq.jpg',
					'https://p.jennandsteve.ca/upload/b4frvof995f.jpg',
					'https://p.jennandsteve.ca/upload/0b18b3qgl3k.jpg',
					'https://p.jennandsteve.ca/upload/2o5b5yr9jhg.jpg',
					'https://p.jennandsteve.ca/upload/316di31inbh.jpg',
					'https://p.jennandsteve.ca/upload/vdtrgvk1ix.jpg',
					'https://p.jennandsteve.ca/upload/yqw8pualqli.jpg',
					'https://p.jennandsteve.ca/upload/ozqbpz0ych.jpg',
					'https://p.jennandsteve.ca/upload/09zdtztxbi.jpg',
					'https://p.jennandsteve.ca/upload/49brzt8p2wf.jpg',
					'https://p.jennandsteve.ca/upload/ry4ta0of64g.jpg',
					'https://p.jennandsteve.ca/upload/pyu2mfjchx.jpg',
					'https://p.jennandsteve.ca/upload/ps0be0kqq8.jpg',
					'https://p.jennandsteve.ca/upload/3awtmw556e.jpg',
					'https://p.jennandsteve.ca/upload/xc1vt6xgar.jpg',
					'https://p.jennandsteve.ca/upload/v7r3ez6ob.jpg',
					'https://p.jennandsteve.ca/upload/ti2vxfd17ag.jpg',
					'https://p.jennandsteve.ca/upload/kaovzsuxxf.jpg',
					'https://p.jennandsteve.ca/upload/kxe21mmcvil.jpg',
					'https://p.jennandsteve.ca/upload/ahyq5plkue.jpg',
					'https://p.jennandsteve.ca/upload/qwoaxx2kqw.jpg',
					'https://p.jennandsteve.ca/upload/23fn6zwquki.jpg',
					'https://p.jennandsteve.ca/upload/mr42zjb4yek.jpg',
					'https://p.jennandsteve.ca/upload/4dlqz4nd7ij.jpg',
					'https://p.jennandsteve.ca/upload/rbleug6gb1.jpg',
					'https://p.jennandsteve.ca/upload/299johbqe6.jpg',
					'https://p.jennandsteve.ca/upload/oriuso63xf.jpg',
					'https://p.jennandsteve.ca/upload/e6bsug20t8.jpg',
					'https://p.jennandsteve.ca/upload/iek505z4he.jpg',
					'https://p.jennandsteve.ca/upload/q5gjgyshqz.jpg',
					'https://p.jennandsteve.ca/upload/q2nc3yhqjg.jpg',
					'https://p.jennandsteve.ca/upload/6ml2okqd56k.jpg',
					'https://p.jennandsteve.ca/upload/mixku0u29yf.jpg',
					'https://p.jennandsteve.ca/upload/wqem7et777.jpg',
					'https://p.jennandsteve.ca/upload/llp4ovnyfb.jpg',
					'https://p.jennandsteve.ca/upload/7h5enij5xn.jpg',
					'https://p.jennandsteve.ca/upload/q2voenfrhk.jpg',
					'https://p.jennandsteve.ca/upload/6hmb1v4y6k.jpg',
					'https://p.jennandsteve.ca/upload/ol9ocqeqde.jpg',
					'https://p.jennandsteve.ca/upload/253bfw0lvp.jpg',
					'https://p.jennandsteve.ca/upload/bi2a6matzf.jpg',
					'https://p.jennandsteve.ca/upload/2c3ilr92bx.jpg',
					'https://p.jennandsteve.ca/upload/txt3mutvon.jpg',
					'https://p.jennandsteve.ca/upload/zn7mixefsw.jpg',
					'https://p.jennandsteve.ca/upload/aqblwgx59rk.jpg',
					'https://p.jennandsteve.ca/upload/c8iasjgvwz.jpg',
					'https://p.jennandsteve.ca/upload/ci72ufuqdp.jpg',
					'https://p.jennandsteve.ca/upload/ggrl1d74x6.jpg',
					'https://p.jennandsteve.ca/upload/n6wezd0nio.jpg',
					'https://p.jennandsteve.ca/upload/2enqh67uj.jpg',
					'https://p.jennandsteve.ca/upload/dp3tqcyt2j.jpg',
					'https://p.jennandsteve.ca/upload/akqovi876u.jpg',
					'https://p.jennandsteve.ca/upload/n82xsx1o9zh.jpg',
					'https://p.jennandsteve.ca/upload/yq9odsaaz5.jpg',
					'https://p.jennandsteve.ca/upload/pkjk6n2tvij.jpg',
					'https://p.jennandsteve.ca/upload/vumvswyomz.jpg',
					'https://p.jennandsteve.ca/upload/6c759fmlxz.jpg',
					'https://p.jennandsteve.ca/upload/tt8531akr0i.jpg',
					'https://p.jennandsteve.ca/upload/fzum2vcnrk.jpg',
					'https://p.jennandsteve.ca/upload/5f3cgnvzpv.jpg',
					'https://p.jennandsteve.ca/upload/v67ccjor64.jpg',
					'https://p.jennandsteve.ca/upload/38qdz7rgnv.jpg',
					'https://p.jennandsteve.ca/upload/q22kqh1v9dl.jpg',
					'https://p.jennandsteve.ca/upload/flon45rpwok.jpg',
					'https://p.jennandsteve.ca/upload/f0e5re8k7g.jpg',
					'https://p.jennandsteve.ca/upload/t99tc99m3wh.jpg',
					'https://p.jennandsteve.ca/upload/kh7m0wrxhc.jpg',
					'https://p.jennandsteve.ca/upload/vdwq4s0ir2.jpg',
					'https://p.jennandsteve.ca/upload/yb7p6u1w53i.jpg',
					'https://p.jennandsteve.ca/upload/v8o2fb80bz.jpg',
					'https://p.jennandsteve.ca/upload/i8136ql1mp.jpg',
					'https://p.jennandsteve.ca/upload/xre0tn5tm0l.jpg',
					'https://p.jennandsteve.ca/upload/5rnboq1p5s.jpg',
					'https://p.jennandsteve.ca/upload/x545zdm3n7.jpg',
					'https://p.jennandsteve.ca/upload/citwwq8rnr.jpg',
					'https://p.jennandsteve.ca/upload/b8yef7a7xof.jpg',
					'https://p.jennandsteve.ca/upload/rawb1wyghl.jpg',
					'https://p.jennandsteve.ca/upload/8vc5b51c4k.jpg',
					'https://p.jennandsteve.ca/upload/07wqdl360df.jpg',
					'https://p.jennandsteve.ca/upload/lq8okgs89l.jpg',
					'https://p.jennandsteve.ca/upload/guvnvlt1ww.jpg',
					'https://p.jennandsteve.ca/upload/kv5c0timej.jpg',
					'https://p.jennandsteve.ca/upload/xflu3xucgz.jpg',
					'https://p.jennandsteve.ca/upload/z7ki2a13q0g.jpg',
					'https://p.jennandsteve.ca/upload/2feafwd9ar.jpg',
					'https://p.jennandsteve.ca/upload/vh23assh7i.jpg',
					'https://p.jennandsteve.ca/upload/toqwizkrzx.jpg',
					'https://p.jennandsteve.ca/upload/wr5qrs2nif.jpg',
					'https://p.jennandsteve.ca/upload/ccr6z37q83.jpg',
					'https://p.jennandsteve.ca/upload/hbzf1xq1jwj.jpg',
					'https://p.jennandsteve.ca/upload/muu4fiygkv.jpg',
					'https://p.jennandsteve.ca/upload/pdh5p1cde7.jpg',
					'https://p.jennandsteve.ca/upload/03e662v9pog.jpg',
					'https://p.jennandsteve.ca/upload/uk7w48fuos.jpg',
					'https://p.jennandsteve.ca/upload/ztzocr5m82.jpg',
					'https://p.jennandsteve.ca/upload/gddhnyawpu.jpg',
					'https://p.jennandsteve.ca/upload/mwr095asbu.jpg',
					'https://p.jennandsteve.ca/upload/o2d13bsm7l.jpg',
					'https://p.jennandsteve.ca/upload/hrxg1w8v24g.jpg',
					'https://p.jennandsteve.ca/upload/7l9nsmtdry.jpg',
					'https://p.jennandsteve.ca/upload/j00qxwvj6u.jpg',
					'https://p.jennandsteve.ca/upload/gz4y1r8s86.jpg',
					'https://p.jennandsteve.ca/upload/2rpnht7okv.jpg',
					'https://p.jennandsteve.ca/upload/at7kl1i6a1.jpg',
					'https://p.jennandsteve.ca/upload/ixwj1uuojn.jpg',
					'https://p.jennandsteve.ca/upload/0h157mtd0k.jpg',
					'https://p.jennandsteve.ca/upload/11h0cp2tq9.jpg',
					'https://p.jennandsteve.ca/upload/dgtbgrzvit.jpg',
					'https://p.jennandsteve.ca/upload/lxjp88avb3.jpg',
					'https://p.jennandsteve.ca/upload/8oqk0zt8jn.jpg',
					'https://p.jennandsteve.ca/upload/iayyc35oao.jpg',
					'https://p.jennandsteve.ca/upload/tws0qqhztc.jpg',
					'https://p.jennandsteve.ca/upload/tegsexly78.jpg',
					'https://p.jennandsteve.ca/upload/8save97wjh.jpg',
					'https://p.jennandsteve.ca/upload/25zbbegirfl.jpg',
					'https://p.jennandsteve.ca/upload/hj9dfkko84.jpg',
					'https://p.jennandsteve.ca/upload/pvv3j6b9qg.jpg',
					'https://p.jennandsteve.ca/upload/ggfa2cv64z.jpg',
					'https://p.jennandsteve.ca/upload/x7mhqo5mlb.jpg',
					'https://p.jennandsteve.ca/upload/cd03zvgx6k.jpg',
					'https://p.jennandsteve.ca/upload/czqqldg9jgi.jpg',
					'https://p.jennandsteve.ca/upload/nhqn7na51p.jpg',
					'https://p.jennandsteve.ca/upload/c7d2l8vxhp.jpg',
					'https://p.jennandsteve.ca/upload/kxt7de001w.jpg',
					'https://p.jennandsteve.ca/upload/6sdacsg3hgl.jpg',
					'https://p.jennandsteve.ca/upload/560yhnbrrk.jpg',
					'https://p.jennandsteve.ca/upload/6i896gvb7.jpg',
					'https://p.jennandsteve.ca/upload/s6b17lrnwf.jpg',
					'https://p.jennandsteve.ca/upload/uyz3iweu5d.jpg',
					'https://p.jennandsteve.ca/upload/0j3fvi6e52.jpg',
					'https://p.jennandsteve.ca/upload/gccrkgoiqtf.jpg',
					'https://p.jennandsteve.ca/upload/blrg6rebc9f.jpg',
					'https://p.jennandsteve.ca/upload/zobqhpumhh.jpg',
					'https://p.jennandsteve.ca/upload/608uhd0cxi.jpg',
					'https://p.jennandsteve.ca/upload/tgwskkv9to.jpg',
					'https://p.jennandsteve.ca/upload/t80kbzob1r.jpg',
					'https://p.jennandsteve.ca/upload/mz9ph4bd6n.jpg',
					'https://p.jennandsteve.ca/upload/ps82h2uvzn.jpg',
					'https://p.jennandsteve.ca/upload/yvv6nd8foz.jpg',
					'https://p.jennandsteve.ca/upload/hf0r5rq2bf.jpg',
					'https://p.jennandsteve.ca/upload/upt1s1zls8.jpg',
					'https://p.jennandsteve.ca/upload/ql4u34tnvj.jpg',
					'https://p.jennandsteve.ca/upload/jkyl29qm3m.jpg',
					'https://p.jennandsteve.ca/upload/4y8ud3xjb3.jpg',
					'https://p.jennandsteve.ca/upload/9i7et5yblb.jpg',
					'https://p.jennandsteve.ca/upload/n92ogpfc2a.jpg',
					'https://p.jennandsteve.ca/upload/x5autk1xzv.jpg',
					'https://p.jennandsteve.ca/upload/u0k2o4m9t1.jpg',
					'https://p.jennandsteve.ca/upload/ifbev4ih42.jpg',
					'https://p.jennandsteve.ca/upload/8eqniw1gv3.jpg',
					'https://p.jennandsteve.ca/upload/uth5cll9z8.jpg',
					'https://p.jennandsteve.ca/upload/2ktw9tm5qx.jpg',
					'https://p.jennandsteve.ca/upload/upawgtv6n3.jpg',
					'https://p.jennandsteve.ca/upload/z2inwbbq23.jpg',
					'https://p.jennandsteve.ca/upload/w7pvy62gzu.jpg',
					'https://p.jennandsteve.ca/upload/e9t557b4pd.jpg',
					'https://p.jennandsteve.ca/upload/qpko5yfxuoj.jpg',
					'https://p.jennandsteve.ca/upload/d4f9f1xwyw.jpg',
					'https://p.jennandsteve.ca/upload/fcxfbjhhyp.jpg',
					'https://p.jennandsteve.ca/upload/c95t547w86.jpg',
					'https://p.jennandsteve.ca/upload/z277n8q3gp.jpg',
					'https://p.jennandsteve.ca/upload/8onadpz3ki.jpg',
					'https://p.jennandsteve.ca/upload/qf8be0aqry.jpg',
					'https://p.jennandsteve.ca/upload/pr20hu9vwi.jpg',
					'https://p.jennandsteve.ca/upload/nehsqf3jxe.jpg',
					'https://p.jennandsteve.ca/upload/as4b87p0te.jpg',
					'https://p.jennandsteve.ca/upload/2om7e82j6r.jpg',
					'https://p.jennandsteve.ca/upload/578fp9kheqj.jpg',
					'https://p.jennandsteve.ca/upload/tbztwbx75rl.jpg',
					'https://p.jennandsteve.ca/upload/a7sc01gr9h.jpg',
					'https://p.jennandsteve.ca/upload/o4hsjyne7c.jpg',
					'https://p.jennandsteve.ca/upload/fi9c9wbwza.jpg',
					'https://p.jennandsteve.ca/upload/f0oyh5sz9e.jpg',
					'https://p.jennandsteve.ca/upload/8nhbx3u8xj.jpg',
					'https://p.jennandsteve.ca/upload/pdjr0cojjg.jpg',
					'https://p.jennandsteve.ca/upload/afidoiwsy4.jpg',
					'https://p.jennandsteve.ca/upload/q16csglu1r.jpg',
					'https://p.jennandsteve.ca/upload/d87dwrl0cn.jpg',
					'https://p.jennandsteve.ca/upload/i1j6dbw2kx.jpg',
					'https://p.jennandsteve.ca/upload/fqkjmk8rtc.jpg',
					'https://p.jennandsteve.ca/upload/59048cm3i0f.jpg',
					'https://p.jennandsteve.ca/upload/xq2lp1prq6f.jpg',
					'https://p.jennandsteve.ca/upload/o1s2g2khq8l.jpg',
					'https://p.jennandsteve.ca/upload/w4m5o4ouwe.jpg',
					'https://p.jennandsteve.ca/upload/bw5gs5da3fg.jpg',
					'https://p.jennandsteve.ca/upload/knz06qwgzl.jpg',
					'https://p.jennandsteve.ca/upload/p88wcw0ioh.jpg',
					'https://p.jennandsteve.ca/upload/d9clzmraqo.jpg',
					'https://p.jennandsteve.ca/upload/61h1h4d9rth.jpg',
					'https://p.jennandsteve.ca/upload/4hi0r4zpyg.jpg',
					'https://p.jennandsteve.ca/upload/0idxpwradw.jpg',
					'https://p.jennandsteve.ca/upload/yrupni3sg3.jpg',
					'https://p.jennandsteve.ca/upload/ztfov7tbrp.jpg',
					'https://p.jennandsteve.ca/upload/ojo32p8naf.jpg',
					'https://p.jennandsteve.ca/upload/74j5e3ytiv.jpg',
					'https://p.jennandsteve.ca/upload/h4mlrn822g.jpg',
					'https://p.jennandsteve.ca/upload/7wohsu4a4c.jpg',
					'https://p.jennandsteve.ca/upload/e9jfsocc9hg.jpg',
					'https://p.jennandsteve.ca/upload/2t6harcbxf.jpg',
					'https://p.jennandsteve.ca/upload/sp987v3261.jpg',
					'https://p.jennandsteve.ca/upload/pmx3xa843r.jpg',
					'https://p.jennandsteve.ca/upload/j1k2s76eprg.jpg',
					'https://p.jennandsteve.ca/upload/2q8y1kd9rn.jpg',
					'https://p.jennandsteve.ca/upload/n01ij1ljmy.jpg',
					'https://p.jennandsteve.ca/upload/7fzzzpsx9c.jpg',
					'https://p.jennandsteve.ca/upload/r1ay7k1h1d.jpg',
					'https://p.jennandsteve.ca/upload/5ue2l8vy46l.jpg',
					'https://p.jennandsteve.ca/upload/1xtycgwhe7.jpg',
					'https://p.jennandsteve.ca/upload/08whp9ylea.jpg',
					'https://p.jennandsteve.ca/upload/5g3tp241et.jpg',
					'https://p.jennandsteve.ca/upload/9a22y8rjpk.jpg',
					'https://p.jennandsteve.ca/upload/5au2hxjhxu.jpg',
					'https://p.jennandsteve.ca/upload/h1zujs196p.jpg',
					'https://p.jennandsteve.ca/upload/1lnnf61icgj.jpg',
					'https://p.jennandsteve.ca/upload/wg0pduqjx5.jpg',
					'https://p.jennandsteve.ca/upload/uxnsanyr2d.jpg',
					'https://p.jennandsteve.ca/upload/83s6kocfd.jpg',
					'https://p.jennandsteve.ca/upload/89i4zomh15.jpg',
					'https://p.jennandsteve.ca/upload/o9rzmu3v9.jpg',
					'https://p.jennandsteve.ca/upload/4c13bmoi03.jpg',
					'https://p.jennandsteve.ca/upload/eaiek2ttso.jpg',
					'https://p.jennandsteve.ca/upload/tee6au5na5.jpg',
					'https://p.jennandsteve.ca/upload/ld7leafpye.jpg',
					'https://p.jennandsteve.ca/upload/c7qb3d8ycm.jpg',
					'https://p.jennandsteve.ca/upload/vu70shx3xz.jpg',
					'https://p.jennandsteve.ca/upload/g8kv13fuks.jpg',
					'https://p.jennandsteve.ca/upload/qm1n5ehclc.jpg',
					'https://p.jennandsteve.ca/upload/zfj7qa0sve.jpg',
					'https://p.jennandsteve.ca/upload/n53fo68s8x.jpg',
					'https://p.jennandsteve.ca/upload/9hmzkh3gby.jpg',
					'https://p.jennandsteve.ca/upload/ntslyepuh3.jpg',
					'https://p.jennandsteve.ca/upload/1o3qg8iagdl.jpg',
					'https://p.jennandsteve.ca/upload/hgftvzf7hj.jpg',
					'https://p.jennandsteve.ca/upload/mp5uvxewzp.jpg',
					'https://p.jennandsteve.ca/upload/jtfcyn9yvs.jpg',
					'https://p.jennandsteve.ca/upload/3ctm65k3s5.jpg',
					'https://p.jennandsteve.ca/upload/t18rdimx67.jpg',
					'https://p.jennandsteve.ca/upload/kkbbn8qgflh.jpg',
					'https://p.jennandsteve.ca/upload/9pjvcd68ks.jpg',
					'https://p.jennandsteve.ca/upload/0ce22qygkx.jpg',
					'https://p.jennandsteve.ca/upload/29xk8kehob.jpg',
					'https://p.jennandsteve.ca/upload/vsy0ehkrp.jpg',
					'https://p.jennandsteve.ca/upload/q9yamwrgm8.jpg',
					'https://p.jennandsteve.ca/upload/tq3ubdp816.jpg',
					'https://p.jennandsteve.ca/upload/e0baidb42u.jpg',
					'https://p.jennandsteve.ca/upload/4z8c2k8btu.jpg',
					'https://p.jennandsteve.ca/upload/rbblhmaipc.jpg',
					'https://p.jennandsteve.ca/upload/0h9ck5en4j.jpg',
					'https://p.jennandsteve.ca/upload/nb1sb11fp2k.jpg',
					'https://p.jennandsteve.ca/upload/izwag7oi4q.jpg',
					'https://p.jennandsteve.ca/upload/yztjiwkpt5j.jpg',
					'https://p.jennandsteve.ca/upload/68ujfnpj98.jpg',
					'https://p.jennandsteve.ca/upload/6d0wa4cwmt.jpg',
					'https://p.jennandsteve.ca/upload/1whor8r6b5.jpg',
					'https://p.jennandsteve.ca/upload/1gryj4k2zt.jpg',
					'https://p.jennandsteve.ca/upload/hks4t8lxkd.jpg',
					'https://p.jennandsteve.ca/upload/erws2tr4ti.jpg',
					'https://p.jennandsteve.ca/upload/7glc4d6qvv.jpg',
					'https://p.jennandsteve.ca/upload/bbuhuk5fam.jpg',
					'https://p.jennandsteve.ca/upload/im8zvjyh4ng.jpg',
					'https://p.jennandsteve.ca/upload/qydhtlhzzk.jpg',
					'https://p.jennandsteve.ca/upload/0njs9608jw.jpg',
					'https://p.jennandsteve.ca/upload/9icj4a11uw.jpg',
					'https://p.jennandsteve.ca/upload/n36ba6tlum.jpg',
					'https://p.jennandsteve.ca/upload/zrt24inept.jpg',
					'https://p.jennandsteve.ca/upload/6jufqf6qlj.jpg',
					'https://p.jennandsteve.ca/upload/yqde5684vk.jpg',
					'https://p.jennandsteve.ca/upload/ftmbw7nzp6.jpg',
					'https://p.jennandsteve.ca/upload/xriuqs02vhj.jpg',
					'https://p.jennandsteve.ca/upload/whkz9z9k67.jpg',
					'https://p.jennandsteve.ca/upload/1ywq3crlyt.jpg',
					'https://p.jennandsteve.ca/upload/l06bslzie6.jpg',
					'https://p.jennandsteve.ca/upload/p2novzp6p3.jpg',
					'https://p.jennandsteve.ca/upload/v1wv98kf9qk.jpg',
					'https://p.jennandsteve.ca/upload/5r3xulpx7a.jpg',
					'https://p.jennandsteve.ca/upload/lnwghjyx3k.jpg',
					'https://p.jennandsteve.ca/upload/vhqcxojx14.jpg',
					'https://p.jennandsteve.ca/upload/9kyeio4kh3.jpg',
					'https://p.jennandsteve.ca/upload/nw9yrw8yt6.jpg',
					'https://p.jennandsteve.ca/upload/tpuauwv2yk.jpg',
					'https://p.jennandsteve.ca/upload/8z3ei90b2k.jpg',
					'https://p.jennandsteve.ca/upload/7c5vzuydnh.jpg',
					'https://p.jennandsteve.ca/upload/potogcmi5k.jpg',
					'https://p.jennandsteve.ca/upload/1qjy9bj4yq.jpg',
					'https://p.jennandsteve.ca/upload/2ptnsbcjit.jpg',
					'https://p.jennandsteve.ca/upload/fjeogj3ray.jpg',
					'https://p.jennandsteve.ca/upload/vuu8elaax6.jpg',
					'https://p.jennandsteve.ca/upload/kt6dek5foz.jpg',
					'https://p.jennandsteve.ca/upload/aarvixi223.jpg',
					'https://p.jennandsteve.ca/upload/jaxojwootr.jpg',
					'https://p.jennandsteve.ca/upload/taa5xz6q02.jpg',
					'https://p.jennandsteve.ca/upload/3dgq0ttskk.jpg',
				],
			};
		},
		reset() {
			Object.assign(this.$data, this.initialState());
		},
	},
};
</script>
