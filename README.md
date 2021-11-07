# gittest

```
	public static void main(String[] args) {
		String str = "최승환ABC123";
		byte[] arr = null;
		List<Byte> byteList = new ArrayList<Byte>();
		try {
			System.out.print("encoding utf-8\nbyte=");
			arr = str.getBytes("utf-8");
			for (byte b : arr) {
				System.out.print((b + 128) + ", ");
			}
			System.out.println("\nutf-8=" + new String(arr, "utf-8"));
			System.out.println("euc-kr=" + new String(arr, "euc-kr"));
			
			System.out.println("-----------------------------------------------------");
			
			System.out.print("encoding euc-kr\nbyte=");
			arr = str.getBytes("euc-kr");
			for (byte b : arr) {
				System.out.print((b + 128) + ", ");
			}
			System.out.println("\neuc-kr=" + new String(arr, "euc-kr"));
			System.out.println("utf-8=" + new String(arr, "utf-8"));

			System.out.println("-----------------------------------------------------");
			
			System.out.print("encoding unicode\nbyte=");
			arr = str.getBytes("unicode");
			for (byte b : arr) {
				if (b < 0) {
					System.out.print((b+256) + ", ");
				} else {
					System.out.print(b + ", ");
				}
			}
			System.out.println("\nunicode=" + new String(arr, "unicode"));
			System.out.println("euc-kr=" + new String(arr, "euc-kr"));
			System.out.println("utf-8=" + new String(arr, "utf-8"));

			System.out.println("-----------------------------------------------------");
			
			System.out.print("encoding euc-kr\nbyte=");
			arr = str.getBytes("euc-kr");
			for (byte b : arr) {
				if (b < 0) {
					System.out.print((b+256) + ", ");
					byteList.add((byte) (b+256));
				} else {
					System.out.print(b + ", ");
					byteList.add((byte) (201));
					byteList.add((byte) (b+129));
//					byteList.add((byte) (b));
				}
			}
			
			byte[] brr = new byte[byteList.size()];
			for (int i = 0; i < byteList.size(); i++) {
				brr[i] = byteList.get(i);
			}
			
			System.out.println("\neuc-kr=" + new String(arr, "euc-kr"));
			System.out.println("utf-8=" + new String(arr, "utf-8"));
			System.out.println("unicode=" + new String(arr, "unicode"));
			System.out.println("utf-8=" + new String(brr, "utf-8"));
			System.out.println("euc-kr=" + new String(brr, "euc-kr"));
			
		} catch (Exception e) {
			e.getStackTrace();
		}
				
	}
```
